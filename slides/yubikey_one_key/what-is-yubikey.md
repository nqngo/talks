<!--
.slide: data-background-image="https://assets2.brandfolder.io/bf-boulder-prod/txcncmqrfr7bqph4kbhwc8/v/49024856/original/5CNFC-iphone-macbook2-1-scaled.jpg" data-background-opacity="0.4"
-->
<h3>What Is <em class="color-yubico-green">YubiKey?</em></h3>

---

- Hardware Security Token.
- Supports *OTP*, *public-key cryptography*, *U2F*, *FIDO2*.
- __OpenPGP smart card__. (*ISO/IEC 7816-4*).
- Can emulates __PIV smart card__. (*PKCS#11*).
- Manufactured by [Yubico Inc](https://yubico.com).
- __Made in USA__.
- Latest version is __Yubikey 5__.

Note:
The YubiKey is a hardware authentication device manufactured by Yubico to protect access to computers, networks, and online services that supports one-time passwords (OTP), public-key cryptography, and authentication, and the Universal 2nd Factor (U2F) and FIDO2 protocols developed by the FIDO Alliance. A YubiKey can also present itself as an OpenPGP card using 1024, 2048, 3072 and 4096-bit RSA (for key sizes over 2048 bits, GnuPG version 2.0 or higher is required) and elliptic curve cryptography (ECC) p256 and p384, allowing users to sign, encrypt and decrypt messages without exposing the private keys. Also supported is the PKCS#11 standard to emulate a PIV smart card. This feature allows for code signing of Docker images as well as certificate based authentication for Microsoft Active Directory and SSH.

Founded in 2007 by CEO Stina Ehrensvärd, Yubico is a private company with offices in Palo Alto, Seattle, and Stockholm. Yubico CTO, Jakob Ehrensvärd, is the lead author of the original strong authentication specification that became known as Universal 2nd Factor (U2F).

YubiKey released the YubiKey 5 series in 2018 which adds support for FIDO2, our presentation will focus on using Yubikey 5 as a OpenPGP card.

- *Summary from https://en.wikipedia.org/wiki/YubiKey*
---

### Other Security Tokens

- [Google Titan Key](https://cloud.google.com/titan-security-key) - U2F only. Made in China.
- [Thetis FIDO2 Security Key](https://thetis.io/collections/fido2/products/thetis-fido2-security-key) - U2F, FIDO2, HOTP. Made in China.
- [Feitian FIDO Card](https://www.ftsafe.com/Products/FIDO/Single_Button_FIDO) - U2F, FIDO2, HOTP, PIV*. Made in China.

Note:
Unfortunately, YubiKey is the only current realistic option in the market at the moment that supports multiple interfaces, allowing us to ultilise one key for multiple functions covered.

The Google Titan Key is rumoured to be manufactured by Feitian Inc.

---

<!--
.slide: data-background-image="https://www.nist.gov/sites/default/files/images/2019/09/25/multifactor-authentificaton.png" data-background-opacity="0.2"
-->

### MFA Recap

1. What you knows. (*Knowledge*)
2. What you have. (*Posession*)
3. What you are. (*Inherence*)
4. Where you are.\* (*Location*)

Note:
1. What you knows example: *password*, *PIN code*, *name of your first ~~love~~ school*.
2. What you have example: *OTP*, *YubiKey*, *phone number*, *SMS code*, *on-device prompt*.
3. What you are example: *fingerprint*, *faceID*, *iris data*, *DNA*.
4. Where you are example: *GPS data*, *location of your network*, *last sign-in location*.
---

<h3>Why <em class="color-yubico-green">YubiKey?</em></h3>
<img src="https://2.bp.blogspot.com/-2FvyOSlV3f8/XN4qy-LbWjI/AAAAAAAAAiY/m6skYaPJodMJgKv_gxtpvWZCwWulyLfxACLcBGAs/s1600/infographic%25402x.png" width="80%" />
<small style="font-size: 1rem;">
Data from <a href="https://security.googleblog.com/2019/05/new-research-how-effective-is-basic.html"><em>Google Security Blog: How effective is basic account hygiene at preventing hijacking (May 17, 2019)<em>
</small>

---

<h3>Why <em class="color-yubico-green">YubiKey?</em> (Cont.)</h3>

- Multi-protocol.
- Supports multi-factors.
- FIDO biometric supports with [YubiKey BIO](https://www.yubico.com/au/store/#yubikey-bio-series-fido-edition).
- Made in USA.
- Cheap. The [YubiKey 5 NFC](https://www.yubico.com/au/product/yubikey-5-nfc/) is $45USD.

---

### What MFA will not prevent

![](https://imgs.xkcd.com/comics/security.png)