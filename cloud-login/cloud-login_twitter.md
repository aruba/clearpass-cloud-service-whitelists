Twitter
======
![version 2017.01](https://img.shields.io/badge/version-2017.01-brightgreen.svg "version 2017.01") ![version 2017.01](https://img.shields.io/badge/source-Aruba_Security-orange.svg "version 2017.01")

![OAuth 2.0](https://img.shields.io/badge/login-OAuth_2.0-blue.svg "OAuth 2.0")
<br>

> OAuth 2.0 configuration > https://dev.twitter.com

## Whitelist
```
api.twitter.com
*.twimg.com
*.twitter.com
```


## Verification and Testing
>__NOTE__: Lack of entry simply means it was not tested.

| | Windows 	| macOS 	| Linux 	| Android 	| iOS 	|
|---------	|---------	|-------	|-------	|---------	|-----	|
|ArubaOS<br>__[ Instant ]__|  Win 10 1703<br> [ 6.5.3 ]	|  	|  	| 7.1 CPB<br> [ 6.5.3 ] 	| 10.3 in CPB<br> [ 6.5.3 ] 	|
|ArubaOS<br>__[ Controller ]__ | Win 10 1703<br> [ 8.1 ] 	| 10.12 CPB<br> [ 8.1 ] 	|  	| 7.1 CPB<br>[ 8.1 ] 	| 10.3 in CPB<br> [ 8.1 ] |

CPB = Captive Portal Browser
<br>

## NAD Examples
### ArubaOS - Controller
```
netdestination cloud-login_twitter
    name api.twitter.com
    name *.twimg.com
    name *.twitter.com
!
```

### ArubaOS - Instant
```
rule alias api.twitter.com match tcp 443 443 permit
rule alias *.twimg.com match tcp 443 443 permit
rule alias *.twitter.com match tcp 443 443 permit
```
