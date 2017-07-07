Azure Active Directory
======
![version 2017.02](https://img.shields.io/badge/version-2017.02-brightgreen.svg "version 2017.02") ![version 2017.02](https://img.shields.io/badge/source-Aruba_Security-orange.svg "version 2017.02")

![SAML](https://img.shields.io/badge/login-SAML-blue.svg "SAML") ![OAuth 2.0](https://img.shields.io/badge/login-OAuth_2.0-blue.svg "OAuth 2.0")
> __LOGIN URL:__ https://login.microsoftonline.com

> Microsoft Login works correctly inside captive portal browsers on Android, iOS and macOS for __login__ flows.

<br>

## Whitelist
```
login.microsoftonline.com
*.aadcdn.microsoftonline-p.com
```


## Verification and Testing
>__NOTE__: Lack of entry simply means it was not tested.

| Windows 	| macOS 	| Linux 	| Android 	| iOS 	|
|---------	|-------	|-------	|---------	|-----	|
| 10, 1703<br>IAP 6.5.3 	|  	|  	| 7.1<br>IAP 6.5.3 	| 9.x<br>IAP 6.5.3 	|
|  	|  	|  	| 7.1<br>ArubaOS 8.1 	|  	|
|  	|  	|  	|  	|  	|

<br>

## NAD Examples
### Aruba Controller
```
netdestination cloud-login_microsoftonline
    name login.microsoftonline.com
    name *.aadcdn.microsoftonline-p.com
!
```

### Aruba Instant
```
 rule alias login.microsoftonline.com match tcp 443 443 permit
 rule alias *.aadcdn.microsoftonline-p.com match tcp 443 443 permit
 rule alias *.aadcdn.microsoftonline-p.com match tcp 80 80 permit
```