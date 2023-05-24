<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2014/07/10/17/18/battleship-389274_960_720.jpg" data-background-opacity="0.2"
-->

## Manage & Operate a Private Cloud

---

## User Experience

- Self-service or managed service?
- Is there budget for help desk and training?
- Is there a service catalog?

Note:
- *Self-service or managed service?:* Understand the choice between providing users with self-service capabilities to manage their own resources or the IT team handles resource provisioning and management on behalf of users. Self-serviceing increases agility and user empowerment and enables users to optimise costs and align their consumption with their specific needs and budget. While managed services ensures consistent configurations, centralised control and cost management to the Ops team.
- *Budget for Help Desk and Training:* Self-service capabilities require users to be trained on how to use the cloud platform. This can be achieved through training courses, documentation, and help desk support.
- *Service Catalog:* A service catalog enables users to easily discover and request the resources they need, improving user experience and ensuring consistent delivery of services.

---
## Infrastructure Management

- Infrastructure as Code (IaC)?
- Service Automation?
- Out-of-band management?
- Incident response playbook?

Note:
- *Infrastructure as Code (IaC):* IaC enables automation, version control, and consistency in infrastructure deployment and configuration changes.In a large scale deployment, it enables faster provisioning, reduced manual errors, and the reliability to reproduce environments.
- *Service Automation:*  It is important to automate routine tasks, such as tenant provisioning, application deployment, and live migration.
- *Out-of-band management:* out-of-band management enables administrators to diagnose and troubleshoot issues even when the primary network is inaccessible. Ensures KVM-over-IP, IPMI, or console servers are available.
- *Incident response playbook:* a well-prepared incident response playbook helps minimise downtime, reduces the impact of incidents, and enhances overall security posture.


---
## Security and Telemetry

- Telemetry and Continuous load testing?
- Security and compliance?
- Capacity planning?
- Active security monitoring?

Note:
- *Telemetry:* gather real-time data and performance metrics about the infrastructure. It helps in proactive monitoring, identifying performance bottlenecks, and optimising resource utilisation.Tools such as Prometheus, Grafana, OpenSearch can be used to implement telemetry.
- *Continuous load testing:* simulate various workload scenarios and ensure the private cloud can handle the expected demand. For example, an hourly test that provisions a new tenant, deploys a new application, and runs a load test then tears down the tenant.
- *Security and compliance:* security measures such as firewalls, encryption, access controls, and identity management to protect data and infrastructure.
- *Capacity planning:* analysing historical usage patterns, forecasting growth, and allocating resources to ensure that the private cloud infrastructure can meet current and future demands.
- *Active security monitoring:* use of intrusion detection systems (IDS), security incident and event management (SIEM) tools, and log analysis to proactively monitor for suspicious activities.
