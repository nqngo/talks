<!--
.slide: data-background-image="https://cdn.discordapp.com/attachments/1014731784291893308/1109468122513166426/weisswolf_a_anatomization_of_a_cloud_to_show_its_anatomy_420c2ff3-6ff4-43bc-abd7-fa470159afb4.png" data-background-opacity="0.4"
-->


# The Cloud Autonomy

---

![Anatomy of a cloud](https://qph.cf2.quoracdn.net/main-qimg-4b471940b270a18fd534e624f852e852)

<small>Source: [_Quora - What is the difference between data centers, cloud and internet?_](https://www.quora.com/What-is-the-difference-between-data-centers-cloud-and-internet)</small>

Note:

Despite leveraging the cloud, it's crucial to understand that data centers remain a vital component in the overall cloud ecosystem. The cloud doesn't eliminate data centers; rather, it transforms the way we interact with and manage them.

The cloud can be viewed as a management layer that sits atop traditional data centers.

---

![](https://cdn.thenewstack.io/media/2020/06/d9fdb83e-brianimage2.jpg)

<small>When you are running a private cloud, you are providing resources abstraction for your users.</small>

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

The absence of data egress or ingress fees, which are common in public cloud models, is also a significant saving factor. This lack of data transfer costs can lead to significant savings, especially for data-intensive operations.

---

## Foundation: Storage

- High value, should always be available.
- Does not directly generate revenue.
- Plan redundancy and replication.
- Plan for backup and disaster recovery.
- Plan for scalability.

Note:
While storage does not generate direct revenue, it is a high-value component of your cloud infrastructure. If your storage goes down, your entire cloud infrastructure goes down.

You need to plan redundancy and replication. For example, if you have a single storage node, you can't have redundancy. The more nodes you have, the more redundancy and replication you can have. However, the more nodes you have, the more expensive your storage system will be.

Backup and disaster recovery solutions are also key components to ensure a company's business continuity. Think tape backup, off-site backup, and disaster recovery sites.

You need to plan for scalability. Circle back to our slide on the importance of scale, capacity not being used is wasted money. You need to plan for dynamic demand to ensure the business can fully take advantage of the cloud but also not overpay for unused capacity.

---

## Network

- Network is the backbone of any cloud infrastructure.
- Scalability and performance are heavily dependent on the network.
- If not designed properly, it can become a bottleneck or single point of failure.

Note:
The network connects all parts of the cloud, making it the foundation for communication and data transfer within your infrastructure. Since usually storage and compute are separated layers, scalability and performance are heavily dependent on the network.

If a network isn't designed properly, it can become a bottleneck that slows down the entire cloud infrastructure. For example, if the network can't handle the volume of data being transmitted, it can slow down data delivery and degrade application performance.

Inadequate network design can also create single points of failure—areas where a problem could disrupt the entire network. For example, if a central router fails and there's no backup, it could take down the whole network.

To prevent these issues, it's important to design your network with redundancy and resiliency in mind. This might involve using redundant network devices, multiple network paths, and automatic failover mechanisms.

---

## Compute

- Provides bare metals, virtual machines (VMs) and containers.
- What your users will interact with.
- Choice between providing a full IaaS or PaaS.
- Can tolerate failure or downtime.
- Highly visible business component.

Note:
Compute is the foundation of any cloud infrastructure. You can choose to provide bare metals, virtual machines (VMs) and containers or only a subset of them.

Decision must be made around providing a full IaaS or PaaS. For example, OpenStack provides a full IaaS suite. Or providing containers only workflow with Kubernetes.

---
## Private Cloud Services

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

<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2014/04/05/11/27/buffet-315691_960_720.jpg" data-background-opacity="1"
-->

Note:
IaaS is like providing a buffet. The customer can choose what they want to eat and how much they want to eat. They can also choose to eat everything or only a subset of the buffet.
