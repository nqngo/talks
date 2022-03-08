<!--
.slide: data-background-image="https://images.unsplash.com/photo-1504384308090-c894fdcc538d" data-background-opacity="0.3"
-->

# Enterprise Usage

<span class="color-yubico-green">Yubikeys</span> in the enterprise environment
<!-- .small -->

---

### Summary

Two ways <span class="color-yubico-green">Yubikeys</span> are deployed:

1. Integration into PIV infrastructure.
2. Self-enrolment with U2F/FIDO2.

---

### PIV Usage

- PIV usage for <span class="color-yubico-green">Yubikeys</span> fell out of popularity.
- Significant burden on IT team for issuance and recovery.
- Requires mini-drivers on the OS*\** to function properly.
- Yubikeys is significantly more expensive than a PIV card.
- Limited adoptation outside US federal government.
- [2021 US National Cybersecurity Excecutive Order](https://www.entrust.com/blog/2021/06/us-cybersecurity-executive-order-and-derived-piv-credential-issuance-with-yubikeys/) sees a revival on PIV usage.

---

### FIDO2 Usage

- Gaining traction as [Zero Trust security model](https://www.okta.com/au/resources/whitepaper-the-state-of-zero-trust-security-2021-report/) is increasing being adopted and the pandemics.
- User self-enrolment reduces IT burden on IT staffs.
- Acceptable trade-off to use Yubikey as main authentication method and TOTP mobile for backup.
- Identity framework such as Okta or Duo helps simplifies MFA authentication implementation.