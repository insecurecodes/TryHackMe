# Day 6

```
X-Pm-Content-Encryption: end-to-end
X-Pm-Origin: internal
Subject: Urgent: Blue section is down. Switch to the load share plan!
From: Chief Elf <chief.elf@santaclaus.thm>
Date: Tue, 6 Dec 2022 00:00:01 +0000
Mime-Version: 1.0
Content-Type: multipart/mixed;boundary=---------------------03edd9c682a0c8f60d54b9e4bb86659f
To: elves.all@santaclaus.thm <elves.all@santaclaus.thm>
X-Attached: Division_of_labour-Load_share_plan.doc
Message-Id: <QW9DMjAyMl9FbWFpbF9BbmFseXNpcw==>
X-Pm-Spamscore: 3
Received: from mail.santaclaus.thm by mail.santaclaus.thm; Tue, 6 Dec 2022 00:00:01 +0000
X-Original-To: elves.all@santaclaus.thm
Return-Path: <murphy.evident@bandityeti.thm>
Delivered-To: elves.all@santaclaus.thm

-----------------------03edd9c682a0c8f60d54b9e4bb86659f
Content-Type: multipart/related;boundary=---------------------8f117c48beda7f1c1da0a5a894d5c4b5

-----------------------8f117c48beda7f1c1da0a5a894d5c4b5
Content-Type: text/html;charset=utf-8
Content-Transfer-Encoding: base64

PHNwYW4+RGVhciBFbHZlcyw8L3NwYW4+PGRpdj48YnI+PC9kaXY+PGRpdj48c3Bhbj5EdWUgdG8g
dGVjaG5pY2FsIHByb2JsZW1zIGluIHRoZSBibHVlIHNlY3Rpb24gb2Ygb3VyIHRveSBmYWN0b3J5
LCB3ZSBhcmUgaGF2aW5nIGRpZmZpY3VsdGllcyBwcmVwYXJpbmcgc29tZSB0b3lzLiA8L3NwYW4+
PC9kaXY+PGRpdj48YnI+PC9kaXY+PGRpdj48c3Bhbj5UaGVyZQogYXJlIGEgZmV3IGRheXMgbGVm
dCB0byBDaHJpc3RtYXMsIHNvIHdlIG5lZWQgdG8gdXNlIHRpbWUgZWZmaWNpZW50bHkgdG8KIHBy
ZXBhcmUgZXZlcnkgd2lzaGxpc3Qgd2UgcmVjZWl2ZS4gRHVlIHRvIHRoYXQsIHRoZSBibHVlIHNl
Y3Rpb24ncyAKd29ya2xvYWQgaXMgc2hhcmVkIHdpdGggdGhlIHJlc3QgdG8gYXZvaWQgYW55IHRv
eSBwcm9kdWN0aW9uIGRlbGF5Ljwvc3Bhbj48L2Rpdj48ZGl2Pjxicj48L2Rpdj48ZGl2PjxzcGFu
PlRoZSBkZXRhaWxlZCBkaXZpc2lvbiBvZiBsYWJvdXIgaXMgaW5jbHVkZWQgaW4gdGhlIGF0dGFj
aGVkIGRvY3VtZW50Ljwvc3Bhbj48L2Rpdj48ZGl2Pjxicj48L2Rpdj48ZGl2PjxzcGFuPkdvb2Qg
bHVjayB0byB5b3UgYWxsLjwvc3Bhbj48L2Rpdj48ZGl2Pjxicj48L2Rpdj48ZGl2PjxiPjxzcGFu
PkNoaWVmIEVsZjwvc3Bhbj48L2I+PC9kaXY+PGRpdj48YnI+PC9kaXY+
-----------------------8f117c48beda7f1c1da0a5a894d5c4b5--
-----------------------03edd9c682a0c8f60d54b9e4bb86659f
Content-Type: application/msword; filename="Division_of_labour-Load_share_plan.doc"; name="Division_of_labour-Load_share_plan.doc"
Content-Transfer-Encoding: base64
Content-Disposition: attachment; filename="Division_of_labour-Load_share_plan.doc"; name="Division_of_labour-Load_share_plan.doc"
```

#### What is the email address of the sender?

{% hint style="info" %}
chief.elf@santaclaus.thm
{% endhint %}

#### What is the return address?

{% hint style="info" %}
murphy.evident@bandityeti.thm
{% endhint %}

#### On whose behalf was the email sent?

{% hint style="info" %}
Chief Elf
{% endhint %}

#### What is the X-spam score?

{% hint style="info" %}
3
{% endhint %}

#### What is hidden in the value of the Message-ID field?

```bash
echo -n "QW9DMjAyMl9FbWFpbF9BbmFseXNpcw==" |base64 -d
```

{% hint style="info" %}
AoC2022\_Email\_Analysis
{% endhint %}

## Visit the email reputation check website provided in the task.&#x20;

#### What is the reputation result of the sender's email address?

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
RISKY
{% endhint %}

## Check the attachments.

#### What is the filename of the attachment?

{% hint style="info" %}
Division\_of\_labour-Load\_share\_plan.doc
{% endhint %}

#### What is the hash value of the attachment?

```bash
emlAnalyzer -i Urgent\:.eml --header --html -u --text --extract-all
```

```
==============
 ||  Header  ||
 ==============
X-Pm-Content-Encryption.....end-to-end
X-Pm-Origin.................internal
Subject.....................Urgent: Blue section is down. Switch to the load share plan!
From........................Chief Elf <chief.elf@santaclaus.thm>
Date........................Tue, 6 Dec 2022 00:00:01 +0000
Mime-Version................1.0
Content-Type................multipart/mixed;boundary=---------------------03edd9c682a0c8f60d54b9e4bb86659f
To..........................elves.all@santaclaus.thm <elves.all@santaclaus.thm>
X-Attached..................Division_of_labour-Load_share_plan.doc
Message-Id..................<QW9DMjAyMl9FbWFpbF9BbmFseXNpcw==>
X-Pm-Spamscore..............3
Received....................from mail.santaclaus.thm by mail.santaclaus.thm; Tue, 6 Dec 2022 00:00:01 +0000
X-Original-To...............elves.all@santaclaus.thm
Return-Path.................<murphy.evident@bandityeti.thm>
Delivered-To................elves.all@santaclaus.thm

 =========================
 ||  URLs in HTML part  ||
 =========================
[+] No URLs found in the html

 =================
 ||  Plaintext  ||
 =================
[+] Email contains no plaintext

 ============
 ||  HTML  ||
 ============
<span>Dear Elves,</span><div><br></div><div><span>Due to technical problems in the blue section of our toy factory, we are having difficulties preparing some toys. </span></div><div><br></div><div><span>There
 are a few days left to Christmas, so we need to use time efficiently to
 prepare every wishlist we receive. Due to that, the blue section's 
workload is shared with the rest to avoid any toy production delay.</span></div><div><br></div><div><span>The detailed division of labour is included in the attached document.</span></div><div><br></div><div><span>Good luck to you all.</span></div><div><br></div><div><b><span>Chief Elf</span></b></div><div><br></div>

 =============================
 ||  Attachment Extracting  ||
 =============================
[+] Attachment [1] "Division_of_labour-Load_share_plan.doc" extracted to eml_attachments/Division_of_labour-Load_share_plan.doc

```

```shell
sha256sum Division_of_labour-Load_share_plan.doc
```

{% hint style="info" %}
0827bb9a2e7c0628b82256759f0f888ca1abd6a2d903acdb8e44aca6a1a03467
{% endhint %}

## Visit the Virus Total website and use the hash value to search.&#x20;

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Navigate to the behaviour section.

#### Navigate to the behaviour section. What is the second tactic marked in the Mitre ATT\&CK section?

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Defense Evasion
{% endhint %}

## Visit the InQuest website and use the hash value to search.&#x20;

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% embed url="https://labs.inquest.net/dfi/sha256/0827bb9a2e7c0628b82256759f0f888ca1abd6a2d903acdb8e44aca6a1a03467" %}

#### What is the subcategory of the file?

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
macro\_hunter
{% endhint %}
