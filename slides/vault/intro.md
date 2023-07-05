<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2015/08/30/23/20/girls-914823_1280.jpg" data-background-opacity="0.1"
-->

## What are <span class="color-yellow-500">**Secrets?**</span>

---

In the context of information technology (IT):

"Secrets are sensitive data such as _API keys_, _credentials_, _tokens_, _certificates_, and _encryption keys_ that are used to protect access to digital resources."

---

### Why are <span class="color-yellow-500">**Secrets**</span> Important?

"Secrets represent privileged access to systems and data, and in the wrong hands, can lead to data breaches, system outages, and other damaging events."

---

## What is <span class="color-yellow-500">**Secrets Management**</span>

---

"Secrets management refers to the practice of handling, controlling, and protecting secrets to prevent unauthorised access to critical systems and data."

In IT, _secrets management_ are synonymous to _automatic secrets management_, not policy frameworks or processes.

---

### Good <span class="color-yellow-500">**Secrets Management**</span>

- Improves Security
- Ensures Regulatory Compliance
- Increases Operational Efficiency
- Reduces Risk of Human Error

Note:

- **Security:** Effective management ensures that only authorised individuals or systems can access sensitive resources. For instance, consider API keys that grant access to cloud resources - mismanagement can lead to unauthorised access and data breaches.
- **Regulatory Compliance:** Regulations like GDPR, HIPAA, and PCI-DSS require specific standards for handling and storing sensitive data. For instance, HIPAA requires secure management of health records, which can include patient login details and encryption keys.
- **Operational Efficiency:** Automated secrets management systems can increase operational efficiency by automating secret rotation and distribution. For example, Amazon's AWS Secrets Manager automatically rotates, manages, and retrieves database credentials, API keys, and other secrets throughout their lifecycle.
- **Reduced Risk of Human Error:** Secrets that are manually managed can be accidentally exposed. For instance, a developer might accidentally commit secrets to a public GitHub repository; an automated system could help prevent this by providing a secure way to access these secrets at runtime without the need to include them in the code.

---

### Poor <span class="color-yellow-500">**Secrets Management**</span>

- Data Breaches
- Compliance Violations and Financial Penalties
- Operational Disruptions
- Damage to Reputation

Note:

- **Unauthorised Access and Data Breaches:** For example, in 2019, a hacker accessed Capital One's data stored on Amazon Web Services by exploiting a misconfigured firewall and gaining access to sensitive credentials:
[https://edition.cnn.com/2019/07/29/business/capital-one-data-breach/index.html](https://edition.cnn.com/2019/07/29/business/capital-one-data-breach/index.html)
- **Compliance Violations and Financial Penalties:** In 2020, the UK's Information Commissioner's Office fined Marriott International £18.4 million for failing to secure personal data in breach of the GDPR.
[https://www.forbes.com/sites/carlypage/2020/10/30/marriott-hit-with-184-million-gdpr-fine-over-massive-2018-data-breach/?sh=5c9112e4b02b](https://www.forbes.com/sites/carlypage/2020/10/30/marriott-hit-with-184-million-gdpr-fine-over-massive-2018-data-breach/?sh=5c9112e4b02b)
- Operational Disruptions: Improper secret management can result in system outages. If critical credentials, such as those needed for a database, are lost or inadvertently changed, it can cause significant downtime.

Damage to Reputation: Breaches due to poor secrets management can harm an organization's reputation, leading to loss of customer trust. The breach of Target's point-of-sale systems in 2013, caused by stolen vendor credentials, affected 40 million credit and debit cards and significantly damaged the company's image.