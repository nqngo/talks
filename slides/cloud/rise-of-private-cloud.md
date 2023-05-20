<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2016/04/20/08/21/entrepreneur-1340649_960_720.jpg" data-background-opacity="0.15"
-->

## The Rise of Private Cloud

---

## Traditional Ops

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle
skinparam linetype ortho

State Business
State Sysadmins
State Developers

Business -right-> Developers
Developers -right-> Sysadmins
Sysadmins -left-> Business

Business: - Give requirements
Business: - Provide funding
Developers: - Write softwares
Developers: - Fix bugs
Sysadmins: - Install softwares
Sysadmins: - Monitor resources
@enduml
```

1. Company is unable to scale _on-demand_.
2. Developers have little visibility on the actual operation loads.
3. Deployment and upgrade are managed centrally by sysadmins.
4. Lack of automation.

---

## Public Cloud Drawbacks

- Cost Unpredictability.
- Compliance and Security Challenges.
- Lack of Control and Customisation.
- Vendor Lock-in.
- Sovereign Risk.

Note: 

- *Cost Unpredictability:* While public clouds operate on a pay-as-you-go model, which can be cost-effective, they can also lead to unpredictable costs. If not carefully managed, resource usage can quickly scale up, leading to unexpectedly high bills.

- *Compliance and Security Challenges:* While many public cloud providers offer tools and certifications to help with compliance, it might be difficult to be fully in compliance of an infrastructure you cannot control. Eg: GDPR, HIPAA, ISM control. Data might accidentally get exposed during testing and production.

- *Lack of Control and Customisation:* With a public cloud, organisations have less control over their infrastructure and data. The cloud provider manages the underlying hardware and software, which can limit customisation and may not meet specific needs. Eg: GPU, TPU, hardware accelerators.

- *Vendor Lock-in:* Migrating to a different cloud provider or on-premise can be complicated and costly.

- *Sovereign Risk:* A country's government will suddenly change its policies or sudden trade embargo, impacting the ability to operate or access data in that country. Eg: in China, strict data sovereignty laws require that data generated in the country must stay in the country. Or recently, AWS has stopped taking new AWS customers in Russia.

Link: https://www.businessinsider.com/amazon-aws-halting-new-customers-in-russia-belarus-2022-3

---
<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2015/11/27/20/28/arno-river-1066307_960_720.jpg" data-background-opacity="0.2"
-->

## Bridging the Gap

- Cost-Predictability
- Control
- Compliance
- Self-service and Agility
- Automation

Note:
- *Cost-Predictability:* Unlike public cloud's pay-as-you-go model, which can lead to unexpected costs, private cloud provides a more predictable cost structure. You own the infrastructure, your infrastructure can depreciate, resell or extend it uses.

- *Control:* With private cloud, the business have complete control over your environment. Your business can tailor the infrastructure to your specific needs. For example, the business might need significant GPU resources but very little demand for high CPU counts.

- *Compliance:* Private cloud makes it easier to comply with various regulations, especially for industries with stringent data security requirements. You control where your data is stored and who has access to it, simplifying compliance management.

- *Self-Service and Agility:* Private cloud brings the self-service convenience of public cloud into your own data center. Developers can quickly and easily access the resources they need, accelerating development cycles and increasing overall business agility.

- *Automation:* Like public clouds, private clouds can incorporate a high degree of automation. This can streamline operations, reduce manual errors, and free up your IT team to focus on strategic initiatives rather than routine tasks.

---

### Industry Trends

![Size of the Private Cloud Services Market During the Forecast 2023-2027 Period](https://www.technavio.com/image/20221127234622_abstract_2023_v1.jpg.webp?v4.1.1) <!-- .element height="50%" width="70%" -->

<small>Source: [_Technavio - Private Cloud Services Market by Service, End-user, and Geography - Forecast and Analysis 2023-2027_](https://www.technavio.com/report/private-cloud-services-market-industry-analysis)</small>
