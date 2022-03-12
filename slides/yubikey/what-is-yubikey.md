<!--
.slide: data-background-image="https://assets2.brandfolder.io/bf-boulder-prod/txcncmqrfr7bqph4kbhwc8/v/49024856/original/5CNFC-iphone-macbook2-1-scaled.jpg" data-background-opacity="0.4"
-->
# What Is <span class="color-yubico-green">YubiKey?</span>

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

### Why <em class="color-yubico-green">YubiKey?</em>

- Multi-protocol.
- Well-documented.
- Supports multi-factors.
- FIDO biometric supports with [YubiKey BIO](https://www.yubico.com/au/store/#yubikey-bio-series-fido-edition).
- Made in USA.
- Cheap. The [YubiKey 5 NFC](https://www.yubico.com/au/product/yubikey-5-nfc/) is $45USD.

---

### What Yubikeys will not prevent

![](https://imgs.xkcd.com/comics/security.png)

<small class="tiny">
<em>Security</em> comic strip from <a href="https://xkcd.com/538/">xkcd.com</a>
</small>
Note:
Yubikey and MFA is part of the _technical solutions_ to assist with securing your credentials. It is a not a tool design
to provide anonymity or complete protection against local authority or state sponsored actors. Know your battle! The scope
of today discussion will not touch the legislative and contractual barriers that preventing you from using Yubikey or similar
devices in your workflow.