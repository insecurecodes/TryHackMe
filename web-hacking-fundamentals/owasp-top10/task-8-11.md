# Task 8\~11

For solving this task, the machine should be started on **Task 8**

Have a look around the web app. The developer has left themselves a note indicating that there is sensitive data in a specific directory.

### What is the name of the mentioned directory? <a href="#what-is-the-name-of-the-mentioned-directory" id="what-is-the-name-of-the-mentioned-directory"></a>

View source code of the page, and found a pattern

```html
<html>
	<head>
		<title>Sense and Sensitivity</title>
		<meta name="viewport" content="width=device-width, user-scalable=no">
		<meta charset="utf-8">
		<link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
		<link type="text/css" rel="stylesheet" href="assets/css/style.css">
		<link type="text/css" rel="stylesheet" href="assets/css/homeStyle.css">
		<link type="text/css" rel="stylesheet" href="assets/css/orkney.css">
	</head>
	<body>
		<header>
			<a id="home" href="/">Sense and Sensitivity</a>
			<a id="login" href="/login">Login</a>
		</header>
		<div class="background"></div>
		<main class="main-text">
			<h1>Welcome to Sense and Sensitivity!</h1>
				
			<p><img src="assets/images/lake-taupo.jpg">You've reached the future world number one in all things therapeutic. We are a startup organisation based in Taupo, New Zealand. Our location near the stunning Lake Taupo lends itself perfectly to our ideology: all mental maladies are curable, you just need to know how! We draw a great deal of inspiration from the genius of Jane Austin, whose great work servers as a beacon from a simpler time.<br> Whilst we are currently still in our beta phase, our aim is ultimately to work with people who are struggling; to learn <em>with</em> them as we work together to combat the dangers of poor mental health. We aim to provide a safe and peaceful environment for those who need it. For the time being we are only accepting beta testers of the program, so please contact us <a href="mailto:beta@senseandsensitivity.xyz">here</a> if you feel like a stay with us amongst some of the most beautiful scenery in the world would be beneficial to you!</p>
		</main>
		<footer><span>&copy; Sense and Sensitivity, 2020</span></footer>
	</body>
</html>
```

#### Answer <a href="#answer" id="answer"></a>

All assets are hosted under /assets

### Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data? <a href="#navigate-to-the-directory-you-found-in-question-one-what-file-stands-out-as-being-likely-to-contain" id="navigate-to-the-directory-you-found-in-question-one-what-file-stands-out-as-being-likely-to-contain"></a>

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### Answer <a href="#answer-1" id="answer-1"></a>

webapp.db

### Use the supporting material to access the sensitive data. What is the password hash of the admin user? <a href="#use-the-supporting-material-to-access-the-sensitive-data-what-is-the-password-hash-of-the-admin-user" id="use-the-supporting-material-to-access-the-sensitive-data-what-is-the-password-hash-of-the-admin-user"></a>

Download the **webapp.db** and open with a program called **sqlitebrowser**

<figure><img src="../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Answer <a href="#answer-2" id="answer-2"></a>

6eea9b7ef19179a06954edd0f6c05ceb

### Crack the hash. What is the admin's plaintext password? <a href="#crack-the-hash-what-is-the-admins-plaintext-password" id="crack-the-hash-what-is-the-admins-plaintext-password"></a>

Using the [crackstation](https://crackstation.net/) we can decrypt the hash

#### Answer <a href="#answer-3" id="answer-3"></a>

qwertyuiop

### Login as the admin. What is the flag? <a href="#login-as-the-admin-what-is-the-flag" id="login-as-the-admin-what-is-the-flag"></a>

[http://10.10.159.22/login/](http://10.10.159.22/login/)

```
user: admin
pass: qwertyuiop
```

#### Answer <a href="#answer-4" id="answer-4"></a>

THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}
