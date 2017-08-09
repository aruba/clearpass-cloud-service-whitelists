ClearPass Onboard - Android
======
![version 2017.01](https://img.shields.io/badge/version-2017.01-brightgreen.svg "version 2017.01") ![version 2017.01](https://img.shields.io/badge/source-Aruba_Security-orange.svg "Aruba Security Group")

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
```


## Verification and Testing
>__NOTE__: Lack of entry simply means it was not tested.

| Android |
|---------|
| 7.0<br>IAP 6.5.3 |
| 7.0<br>ArubaOS 8.1.0.1 |

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
```
