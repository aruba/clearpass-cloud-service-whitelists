ClearPass Onboard - Android
======
![version 2018.01](https://img.shields.io/badge/version-2018.01-brightgreen.svg "version 2018.01") ![version 2018.01](https://img.shields.io/badge/source-Aruba_Security-orange.svg "Aruba Security Group")

![ClearPass Onboard](https://img.shields.io/badge/ClearPass-Onboard-blue.svg "ClearPass Onboard") ![Android](https://img.shields.io/badge/Platform-Android-blue.svg "Android")

> Certificate enrollment on Android requires the QuickConnect app from the Google Play store and also requires bypassing the restricted Android captive portal browser. These are the names required to be whitelisted on the network device in the pre-authentication state.



## Whitelist
```
android.clients.google.com
*.googleapis.com
*.gvt1.com
*.ggpht.com
*.googleusercontent.com
*.gstatic.com
clients.l.google.com
accounts.google.com
accounts.youtube.com
connectivitycheck.android.com
connectivitycheck.gstatic.com
www.google.com
```


## Verification and Testing
>__NOTE__: Lack of entry simply means it was not tested.

| Android Version | Android Device | Network Access Device |
|---------|---------|---------|
| 7.0 (Nougat) | | ArubaOS 6.5.3 (Instant) |
| 8.1.0 (Oreo) | Pixel 2 XL | ArubaOS 8.3.0.0 (controller) |
| 9.0 DP4 (Android P) | Pixel 2 | ArubaOS 8.3.0.0 (controller) |

<br>

## NAD Examples
### Aruba Controller
```
netdestination onboard-googleplay
    name android.clients.google.com
    name *.googleapis.com
    name *.gvt1.com
    name *.ggpht.com
    name *.googleusercontent.com
    name *.gstatic.com
    name clients.l.google.com
    name accounts.google.com
    name accounts.youtube.com
    name connectivitycheck.android.com
    name connectivitycheck.gstatic.com
    name www.google.com
!
aaa authentication captive-portal <captive-portal-profile-name>
    white-list onboard-googleplay
!
```

### Aruba Instant
```
rule alias android.clients.google.com match tcp 443 443 permit
rule alias googleapis.com match tcp 443 443 permit
rule alias gvt1.com match tcp 443 443 permit
rule alias ggpht.com match tcp 443 443 permit
rule alias googleusercontent.com match tcp 443 443 permit
rule alias gstatic.com match tcp 443 443 permit
rule alias clients.l.google.com match tcp 443 443 permit
rule alias accounts.google.com match tcp 443 443 permit
rule alias accounts.youtube.com match tcp 443 443 permit
rule alias connectivitycheck.android.com match tcp 80 80 permit
rule alias connectivitycheck.android.com match tcp 443 443 permit
rule alias connectivitycheck.gstatic.com match tcp 80 80 permit
rule alias connectivitycheck.gstatic.com match tcp 443 443 permit
rule alias www.google.com match tcp 443 443 permit
rule alias www.google.com match tcp 80 80 permit
```

### Cisco WLC 8.2+
```
acl url-domain add android.clients.google.co ONBOARD
acl url-domain add googleapis.co ONBOARD
acl url-domain add gvt1.co ONBOARD
acl url-domain add ggpht.co ONBOARD
acl url-domain add googleusercontent.co ONBOARD
acl url-domain add gstatic.co ONBOARD
acl url-domain add clients.l.google.co ONBOARD
acl url-domain add accounts.youtube.co ONBOARD
acl url-domain add accounts.youtube.co ONBOARD
acl url-domain add connectivitycheck.android.co ONBOARD
acl url-domain add connectivitycheck.gstatic.co ONBOARD
acl url-domain add www.google.co ONBOARD
```
## Change Log
* 2018.01 (2018-07-06)
    * Added _www.google.com_, required for Android 8.X+
    * Tested ArubaOS 8.3.0.0 (controller) with Android Oreo (8) and Android P (9 Developer Preview 4)

