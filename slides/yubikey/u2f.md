<!--
.slide: data-background-image="https://thumb.tildacdn.com/tild3062-3032-4636-a539-383034373633/-/format/webp/lock5.png" data-background-opacity="0.3"
-->

# <span class="color-yellow-500">U2F</span>

<small>Universal 2nd Factor</small>

---

### Summary

- Open standard that simplifies 2FA using USB or NFC smart cards.
- Initially developed by *Google* and *Yubico*.
- Standard is hosted by *FIDO Alliance*.
- Succeed and extended by *FIDO2*.

---

### Example <span class="color-yellow-500">U2F</span> Supported Services

<div class="container">
    <div class="col">
        <ul>
            <li><a href="https://support.google.com/accounts/answer/6103523">Google</a></li>
            <li><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_u2f.html">Amazon AWS</a></li>
            <li><a href="https://support.cloudflare.com/hc/en-us/articles/200167906-Securing-user-access-with-two-factor-authentication-2FA-#6Gqe6f3nZtXSTpwyS2PBZ1">Cloudflare</a></li>
            <li><a href="https://help.okta.com/en/prod/Content/Topics/Security/mfa/u2f-security-key.htm">Okta</a></li>
            <li><a href="https://www.facebook.com/help/401566786855239">Facebook</a></li>
            <li><a href="https://www.yubico.com/au/works-with-yubikey/catalog/?protocol=4&series=3&sort=popular">And many mores...</a></li>
        </ul>
    </div>
    <div class="col" />
</div>

---

### <span class="color-yellow-500">U2F</span> Sign-In Example

<div class="r-stack">
    <img class="fragment fade-out" data-fragment-index="0" src="https://2.bp.blogspot.com/--q3Fde6j7rI/W-4P-CWsN4I/AAAAAAAAHZc/1zTeAhBWeDg7bDI-oTl_E9V9mb3hNKbcgCLcBGAs/s640/Sign%2Bin%2Bscreen%2Bnew.png">
    <img class="fragment current-visible" data-fragment-index="0" src="https://i.pcmag.com/imagery/reviews/00dPzZkdHgKapBbjEIsWijy-4.fit_lim.size_725x827.v_1569469927.png">
</div>

<small class="tiny">
Images from <a href="https://workspaceupdates.googleblog.com/2018/11/changes-to-google-sign-in-interface.html">Google Blog</a> and <a href="https://www.pcmag.com/reviews/yubico-yubikey-5-nfc">PCMag</a>
</small>

---

### How does it work?

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

participant Device
participant Browser
participant Server

Browser-// Server: username+password

note over Server: verify password
note over Server: gnenerate challenge

Server -// Browser: challenge

Browser -> Device: challenge

note over Device: user touches button

Device --> Browser: response

Browser -// Server: response

note over Server: verify response
```

<br >
<small>
Process flow diagram provided by <a href="https://developers.yubico.com/U2F/"> Yubico</a>
</small>

---
### <span class="color-yellow-500">Observed</span> issues

- No limitation on how many U2F site used.
- Not possible to duplicate key.
- Some sites do not allow multiple hardware keys.