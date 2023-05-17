# The Cloud Autonomy

---

![Anatomy of a cloud](https://qph.cf2.quoracdn.net/main-qimg-4b471940b270a18fd534e624f852e852)

<small>Source: [_Quora - What is the difference between data centers, cloud and internet?_](https://www.quora.com/What-is-the-difference-between-data-centers-cloud-and-internet)</small>

Note:

Despite leveraging the cloud, it's crucial to understand that data centers remain a vital component in the overall cloud ecosystem. The cloud doesn't eliminate data centers; rather, it transforms the way we interact with and manage them.

The cloud can be viewed as a management layer that sits atop traditional data centers.

---
## Cloud Components

![](http://netapp.github.io/openstack-deploy-ops-guide/mitaka/content/figures/1/a/images/OpenStack%20Architecture.png)

Note:

- **Compute:** Enables provisioning and management of virtual machines, accessible via APIs and web interfaces. Designed to scale horizontally and integrate with existing systems.
- **Block Storage:** Offers "block storage as a service" with persistent block devices mapped to compute instances. Manages creation, attaching, detaching, and supports instance booting and cloning.
- **Object Storage:** Provides distributed, scalable storage for static data like images, backups, and archives. Uses an API-accessible platform and proposes an open standard for cloud storage.
- **Dashboard:** Graphical interface for accessing, provisioning, and automating cloud-based resources. Easily integrates third-party products and services.
- **Identity:** Acts as a central directory for user authentication and authorisation across the cloud operating system. Supports various forms of authentication and integrates with existing directories.
- **Image Service:** Offers image registration, delivery, and storage services. Enables quick provisioning of new servers using pre-stored images and allows backups and snapshots.
- **Network Service:** Manages networks and IP addresses with scalability and API-driven control. Ensures the network is not a limiting factor and supports software-defined networking (SDN) technology.
- **Telemetry:** Collects usage and performance data within a cloud environment. Primarily focuses on monitoring and metering.
- **Orchestration:** Orchestrates multiple composite cloud applications using a template format. Facilitates workload management and deployment across cloud environments.

---

## Foundation: Storage

- Data is the **critical** business assets.
- Main reasons for private cloud:
  - Reduction of latency.
  - Control over data and data governance.
- Absence of data ingress-egress fee.
- Provides block, object, and file storage.

Note:
In today's digital age, data is not just an asset - it is a critical business asset. The way an organisation stores, manages, and accesses this data can significantly impact its success.

Having direct control over the storage infrastructure can help optimize performance and reduce latency. Especially if your data set is huge. For example, the Large Hadron Collider experience at CERN produces 10TB/s of raw data. Eg:[https://www.nature.com/articles/s41597-022-01187-8](https://www.nature.com/articles/s41597-022-01187-8)

In a private cloud, organisations have full control over where their data is stored and who can access it, which is crucial for adhering to data regulations and maintaining data privacy.

The absence of data egress or ingress fees, which are common in public cloud models. This lack of data transfer costs can lead to significant savings, especially for data-intensive operations.

---

## Foundation: Storage (Cont.)

- Plan redundancy and replication.
- Plan for backup and disaster recovery.
- Plan for data migration.

Note:
You need to plan redundancy and replication. For example, if you have a single storage node, you can't have redundancy. If you have two storage nodes, you can have redundancy. If you have three storage nodes, you can have redundancy and replication. The more nodes you have, the more redundancy and replication you can have. The more redundancy and replication you have, the more fault-tolerant your storage system will be. However, the more nodes you have, the more expensive your storage system will be.

Backup and disaster recovery solutions are also key components to ensure a company's business continuity. Think tape backup, off-site backup, and disaster recovery sites.

Data migration is also crucial. Generally, this is the result of introducing a new system or location for the data. The business drivers for data migration vary, but common ones include: Data center relocation or consolidation, server or storage equipment refresh, application migration, application upgrade, and data center expansion.

---

## Foundation: Compute

- Provides bare metals, virtual machines (VMs) and containers.
- Choice between providing a full IaaS or PaaS.
- Provides a self-service portal for provisioning and management.
- Provides a set of APIs for integration with other systems.

Note:
Compute is the foundation of any cloud infrastructure. You can choose to provide bare metals, virtual machines (VMs) and containers or only a subset of them.

Decision must be made around providing a full IaaS or PaaS. IaaS provides the infrastructure, while PaaS provides the infrastructure and the platform. For example, OpenStack provides a full IaaS suite. Or providing containers only workflow with Kubernetes.
