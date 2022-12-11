# Day 7

{% embed url="https://gchq.github.io/CyberChef/" %}

### What is the version of CyberChef found in the attached VM?

![](<../../.gitbook/assets/image (8).png>)![](<../../.gitbook/assets/image (20).png>)

{% hint style="info" %}
9.49.0
{% endhint %}

### How many recipes were used to extract URLs from the malicious doc?

1. strings
2. Find / Replace
3. Drop bytes
4. From base64
5. Decode text
6. Find/Replace (to remove patterns)
7. Find/Replace
8. Extract URLs
9. Split
10. Defang URL

{% hint style="info" %}
10
{% endhint %}

### We found a URL that was downloading a suspicious file; what is the name of that malware? 

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Last step will solve the next 3 questions

{% hint style="info" %}
mysterygift.exe
{% endhint %}

### What is the last defanged URL of the bandityeti domain found in the last step?

{% hint style="info" %}
hxxps\[://]cdn\[.]bandityeti\[.]THM/files/index/
{% endhint %}

### What is the ticket found in one of the domains? (Format: Domain/\<GOLDEN\_FLAG>)

{% hint style="info" %}
THM\_MYSTERY\_FLAG
{% endhint %}
