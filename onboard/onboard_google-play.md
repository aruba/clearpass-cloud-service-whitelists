Google Accounts
======
![version 2017.01](https://img.shields.io/badge/version-2017.01-brightgreen.svg "version 2017.01")

![SAML](https://img.shields.io/badge/login-SAML-blue.svg "SAML") ![OAuth 2.0](https://img.shields.io/badge/login-OAuth_2.0-blue.svg "OAuth 2.0")
> Used for both Google consumer login and G Suite (unified login)

<br>

## FQDN List
```
accounts.google.com
accounts.youtube.com
clients.l.google.com
ssl.gstatic.com
googlehosted.l.googleusercontent.com
lh3.googleusercontent.com
```

## NAD Examples
### Aruba Controller
```
netdestination social-login_google
    name accounts.google.com
    name accounts.youtube.com
    name clients.l.google.com
    name ssl.gstatic.com
    name googlehosted.l.googleusercontent.com
    name lh3.googleusercontent.com
!
```

<br>

### Aruba Instant
```
 rule alias accounts.google.com match tcp 443 443 permit
 rule alias accounts.youtube.com match tcp 443 443 permit
 rule alias clients.l.google.com match tcp 443 443 permit
 rule alias ssl.gstatic.com match tcp 443 443 permit
 rule alias googlehosted.l.googleusercontent.com match tcp 443 443 permit
 rule alias connectivitycheck.gstatic.com match tcp 443 443 permit
 rule alias connectivitycheck.gstatic.com match tcp 80 80 permit
 rule alias connectivitycheck.android.com match tcp 443 443 permit
 rule alias connectivitycheck.android.com match tcp 80 80 permit
 rule alias lh3.googleusercontent.com match tcp 443 443 permit
```