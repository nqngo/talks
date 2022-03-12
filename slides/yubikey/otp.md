<!--
.slide: data-background-image="https://static.vecteezy.com/system/resources/previews/002/283/197/large_2x/one-time-password-illustration-concept-vector.jpg" data-background-opacity="0.3"
-->

# <span class="color-yubico-green">OTP</span>

<small>One-Time Password</small>

---

### Summary

- De facto standard for MFA implementation.
- Use a __seed__ and a __moving factor__ to generate OTP code.
- 2 implementations: __HOTP__ and __TOTP__.
- Yubikey only supports __HOTP__.
- __TOTP__ is supported via [Yubico Authenticator](https://support.yubico.com/hc/en-us/articles/360013789259-Using-Your-YubiKey-with-Authenticator-Codes).

---

### OTP Inherit Weakness

- _Man-in-the-middle_ attack.
- Possible to steal the *seed* and derive *moving factor*.

---

### <span class="color-yubico-green">HOTP</span>
- Stands for __HMAC-based One-time Password__.
- __HMAC__: Hash-based Message Authentication Code.
- *Moving factor* is a counter.
- OTP generator and the server are synced **counter** each time a valid code is used.
- Usually implement a *look-ahead* window to prevent desync from too many clicks.
- More susceptible to brute force attack.
- Yubikey only supports __HOTP__.

---

### <span class="color-yubico-green">TOTP</span>
- Stands for __Time-based One-time Password__.
- *Moving factor* is time-based.
- Amount of time each password is valid is called a *timestep*.
- Potential for time-drift.
- Yubikey does not have a built-in clock.
- Relies on *Yubico Authenticator* to provide correct time.
- No significant advantage over phone authenticator apps.

---

### How to setup on <span class="color-yubico-green">Yubikey</span>

- Configuring Yubikey [__HOTP__](https://duo.com/docs/yubikey).
- Configuring Yubikey for [__TOTP__ with *Yubico Authenticator*](https://support.yubico.com/hc/en-us/articles/360013789259-Using-Your-YubiKey-with-Authenticator-Codes).

---

### Issues

- Cumbersome vs. using the phone.
- Does not solve _Man-in-the-middle_ attack.
- Limited amount of key slots available.