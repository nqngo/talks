<!--
.slide: data-background-image="https://images.unsplash.com/photo-1558494949-ef010cbdcc31" data-background-opacity="0.3"
-->

# <span class="color-yubico-green">PIV</span>

<small>PKCS#11 smart card & X.509</small>

---

### Summary

- US federal government standard in 2004 to enhance physical, cyber security and cross-agency cooperation.
- Reliant on _“cryptographic keys”_ in the form of X.509 digital certificates.
- In practice, _<span class="color-yubico-green">Yubikey</span>_ is a smart card that can securely store _5-25_* X.509 certificates.
- A PKI and AD are required to sign and match certificates against known user.

---

### Use Case: <span class="color-yellow-400">System Login</span>

- [Use PIV for SSH login](https://blog.asksven.io/posts/ssh-login-with-yubikey/) on Ubuntu.
- [Smart card-only login](https://support.apple.com/en-us/HT208372) for your Macbook.
- Use [Slot 9a: PIV Authentication](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html).
- PIN asked _once_.
---

### Use Case: <span class="color-yellow-400">Digital Signature</span>

- [Use Yubikey to sign digital signature](https://support.yubico.com/hc/en-us/articles/4412049077522-YubiKeys-for-Digital-Signature-in-Adobe-Acrobat-Reader-Windows-) in Adobe Reader PDF.
- [Sign Docker image](https://ruimarinho.gitbooks.io/yubikey-handbook/content/docker-content-trust/pushing-signed-image/generating-the-root-key.html) using the Yubikey.
- Use [Slot 9c: Digital Signature](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html).
- PIN _always_ asked.

---

### Use Case: <span class="color-yellow-400">Key Management</span>
- [Signing your email with S/MIME certificate](https://andrewmatveychuk.com/signing-your-emails-in-outlook-with-an-s-mime-certificate-and-yubikey/).
- [Signing your git commit with S/MIME certificate](https://enjoi.dev/posts/2021-09-30-signing-git-commits-using-s-mime-x509-certificates/).
- Use [Slot 9e: Key Management](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html).
- PIN asked _once_.

---

### Use Case: <span class="color-yellow-400">Attestation</span>

- Attest keys in other slots are generated on Yubikey itself.
- No duplicated copies lying around.
- Secured with a PIN.
- Yubico has a native attestation certificate in [Slot f9: Attestation](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html).

Note:

**Attestation** means the same thing in cybersecurity as it does in the legal world – it’s a signature that verifies the origin of a document, or in this case, a digital certificate.

Attestation for digital certificates is usually performed on the device that the certificate is being issued to. That’s a critical component of attestation because the only time digital certificates are vulnerable to being compromised is when they are being distributed to client devices. On-device attestation proves that the certificate was generated locally and is uncompromised.

In order to generate and attest a legitimate digital certificate you need to have a secure cryptoprocessor such as a hardware security module (HSM) or PIV-enabled smartcard on the device itself, as is the case with several Yubico products.

That allows verifiers to tie private key operations to a specific entity. For example, if a public key verifies a digital signature, and that public key is certified by a certificate (and the certificate verifies, see chaining below), then the signature is said to belong to the name on the certificate.

---

### Using <span class="color-yubico-green">Yubikey</span> PIV for yourself

- Rarely used and advocated as a personal tool.
- Usually only applicable in a large enterprise environment.
- Required PKI to be setup.
- Most likely use case for this mode is _Docker Content Trust_ Signing.
- Extra complexity juggling multiple certificates.
- Realistically, only 4 slots; the extra slots might not be supported by software.