# Day 3

### What is the name of the Registrar for the domain santagift.shop?

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

```bash
whois santagift.shop |grep -i registrar
```

{% hint style="info" %}
Namecheap Inc
{% endhint %}

### Find the website's source code (repository) on [github.com](https://github.com/) and open the file containing sensitive credentials. Can you find the flag?

Repo link

{% embed url="https://github.com/search?q=santagiftshop" %}

![](<../../.gitbook/assets/image (5).png>)

{% hint style="info" %}
{THM\_OSINT\_WORKS}
{% endhint %}

### What is the name of the file containing passwords?

{% hint style="info" %}
config.php
{% endhint %}

## What is the name of the QA server associated with the website?

In the `README.md` description shows:

{% hint style="info" %}
`qa.santagift.shop`
{% endhint %}

### What is the DB\_PASSWORD that is being reused between the QA and PROD environments?

Inside the `config.php` website we can find the <mark style="color:red;background-color:red;">DB\_PASSWORD</mark> variable with the value:&#x20;

{% hint style="info" %}
S@nta2022
{% endhint %}
