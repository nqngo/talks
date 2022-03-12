<!--
.slide: data-background-image="https://bloksec.com/wp-content/uploads/2020/09/Passwordless-auth@4x.png" data-background-opacity="0.3"
-->

# <span class="color-yellow-500">FIDO2</span>

<small>and the road to <strong class="color-yubico-green">Passwordless</strong></small>

---

### Summary

- FIDO2 is an extension of __FIDO U2F__.
- Standard current supported by *FIDO Alliance*.
- Augment __U2F__ hardware authentication with on-device PIN or biometrics.
- [WebAuthn](https://webauthn.guide/) (core component) officially become a [web standard since 2019](https://www.w3.org/2019/03/pressrelease-webauthn-rec.html.en).
- Introduce process for [Passwordless authentication](https://duo.com/blog/the-passwordless-future-is-here-are-you-ready).

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
participant "Relying Party" as RP
participant "FIDO2 Service" as Auth

Browser -> RP: initiate auth
RP -> Auth: request auth
Auth --> RP: if first time, create user
Auth -> RP: challenge response
RP -> Browser: forward response

note over Browser: verify Relying Party\n & OS subsystem

Browser -> Device: prompt authenticator
note over Device: If first time, create\n a Resident Key
Device -> Browser: sign assertation

Browser -> RP: send assertation response
RP -> Auth: forward response

note over Auth: verify assertation
Auth -> RP: return verification result
```

---

### Supported vendors <span class="color-yubico-blue">today</span>


<div class="container">
    <div class="col">
        <ul>
            <li><a href="https://www.okta.com/demos/passwordless-authentication-with-okta/">Okta</a></li>
            <li><a href="https://www.cisco.com/c/en/us/products/security/threatwise-tv-demos/duo-passwordless-authentication.html">Duo</a></li>
            <li><a href="https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-passwordless">Microsoft Azure</a></li>
        </ul>
    </div>
    <div class="col" />
</div>

---

### <span class="color-yubico-blue">Microsoft Azure</span> Demo

![](https://docs.microsoft.com/en-us/azure/active-directory/authentication/media/concept-authentication-passwordless/concept-web-sign-in-security-key.png)


---

### Why <span class="color-yubico-green">Passwordless</span> is not everywhere yet?

- Significantly more complex than <span class="color-yellow-400">U2F (CTAP1)</span> to implement.
- Most implementation relying on external services.
- Low adoption of hardware keys.
- Yubikey 5 can only support up to [25 Resident Keys](https://support.yubico.com/hc/en-us/articles/360013647720-Security-Key-by-Yubico).