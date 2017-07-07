Okta
======
![version 2017.01](https://img.shields.io/badge/version-2017.01-brightgreen.svg "version 2017.01") ![version 2017.01](https://img.shields.io/badge/source-Okta-orange.svg "version 2017.01")

![SAML](https://img.shields.io/badge/login-SAML-blue.svg "SAML") ![OAuth 2.0](https://img.shields.io/badge/login-OAuth_2.0-blue.svg "OAuth 2.0")
> __LOGIN URL:__ https://_< tenant >_.okta.com

> Okta login works correctly inside captive portal browsers on Android, iOS and macOS for __login__ flows.

<br>

## Whitelist
```
*.okta.com
*.oktapreview.com
*.oktacdn.com
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
    name *.okta.com
    name *.oktapreview.com
    name *.oktacdn.com
!
```

### Aruba Instant
```
 rule alias *.okta.com match tcp 443 443 permit
 rule alias *.oktapreview.com match tcp 443 443 permit
 rule alias *.oktacdn.com match tcp 443 443 permit
 rule alias *.oktacdn.com match tcp 80 80 permit
```