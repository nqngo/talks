<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2016/11/04/20/14/door-1798851_1280.jpg" data-background-opacity="0.1"
-->

## Types of Secrets

---

Can be grouped into 4 broad categories:
- **Static Secrets**
- **Dynamic Secrets**
- **Certificates**
- **Personal Identifiable Information (PII)**

---

<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2018/05/16/18/42/security-3406723_1280.jpg" data-background-opacity="0.1"
-->


## Static Secrets

---

- Secrets that are created and changed manually.
- Examples included:
  - **Passwords:** database, SaaS accounts...
  - **API keys:** AWS, Azure, OpenAI...
  - **Access tokens:** GitHub, GitLab...

---

### Issues with Static Secrets

- Usually mandated by the service provider.
- Might not be possible to automate the creation and rotation of these secrets.
- Might not be possible to region-lock access.
- Might need to be socialised with members of organisation.

---

### Securing Static Secrets

- <span class="color-openstack-red">**DO NOT**</span> embed them in code or version control.
- <span class="color-openstack-red">**DO NOT**</span> share them over insecure channels.
- Apply the principle of least privilege.
- Enable multi-factor authentication (MFA) where possible.

Note:
- Don't expose static secrets in code or version control. This is a common mistake that can lead to a lot of problems.
[https://dev.to/juanmanuelramallo/i-was-billed-for-14k-usd-on-amazon-web-services-17fn](https://dev.to/juanmanuelramallo/i-was-billed-for-14k-usd-on-amazon-web-services-17fn)
- Don't share static secrets over insecure channels. This includes email, Slack, and other chat applications.
- Apply the principle of least privilege. Only give access to the secrets that are needed. This is especially important for static secrets. For example, if a user only needs read access to a database, don't give them write access. If possible, use your static secrets to create short-lived dynamic secrets. This will help to reduce the risk of static secrets being compromised.
- Enable multi-factor authentication (MFA) where possible. This will help to reduce the risk of static secrets being compromised and add an extra layer of security.

---

<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2012/04/13/21/17/ticket-33657_1280.png" data-background-opacity="0.1" data-background-position="left top" data-background-repeat="repeat"
-->

## Dynamic Secrets

---

- Secrets that are created and changed automatically.
- Usually have a very limited lifetime (e.g. < 1h).
- Can be restricted to a system, user, or IP address.
- Examples included:
  - **Database credentials**
  - **Cloud provider credentials**: AWS, Azure...
  - **One-time passwords (OTP)**

---

### Issues with Dynamic Secrets

- Secrets synchronisation.
- Dependency on external services.
- Disaster recovery and backup.
- Scalability.
- Break-glass scenarios.

Note:

- **Secrets synchronisation:** If you rotate a secret, you need to make sure that all the systems that use that secret are updated. This can be difficult to manage at scale.
- **Dependency on external services:** If the service that manages your secrets goes down, you might not be able to access your systems.
- **Disaster recovery and backup:** If you lose access to your secrets, you might not be able to recover your systems.
- **Scalability:** If you have a large number of secrets, how do you ensure your secret management system can handle the load?
- **Break-glass scenarios:** If you lose access to your secret management system, how do you recover?

---

### Securing Dynamic Secrets

- Use a secret management system, avoid programming your own.
- Use a system that supports high availability (HA) and disaster recovery (DR).
- Think horizontally scaling, avoid vertical scaling.
- Code defensively, assume that your secret management system will fail. Retry failed requests, implement circuit breakers, and have a fallback plan.
- Since credentials are created and changed automatically, ensure a proper monitoring and alerting system is in place.

---

<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2022/07/14/12/48/view-7321141_1280.png" data-background-opacity="0.8" data-background-color="rgba(111, 112, 112, 0.5)"
-->

## <span class="color-yellow-500">Certificates</span>

---

- Binary data that is used to establish trust between two parties.
- Usually issued by a certificate authority (CA).
- Examples included:
  - **TLS certificates**
  - **SSH certificates**
  - **Code signing certificates**

---

### Issues with Certificates

- Certificate can expire, revoked or compromised.
- Certificate can be issued by a malicious CA.
- Certificate can be issued to a malicious party.
- Complex to manage at scale.

---

### Securing Certificates

- Use strong encryption algorithms.
- Monitor certificate expiry.
- Avoid using self-signed certificates.
- Store certificates in a secure location.

---

<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2022/02/27/04/58/fingerprint-7036681_1280.png" data-background-opacity="0.1"
-->

## Personal Identifiable Information (PII)

---

- Information that can be used to identify an individual.
- Usually needs to be retrieved and could not be hashed.
- Usually unchangeable.
- Examples included:
  - **Driver's license number**
  - **Passport number**
  - **Social security number (SSN)**
  - **Credit card number**

---

### Issues with PII

- Highly valuable to attackers.
- Usually stored in plain text.
- Asymmetric encryption is not an option.
- Serious legal and financial consequences.

---

### Securing PII

- Not storing PII is the best option.
- **DO NOT** use real PII in test and dev.
- Encrypting the data both at rest and in transit.
- Strong access controls.
- Delete PII when it is no longer needed.
- Regularly audit and monitor usage of PII in your systems.
