<!--
.slide: data-background-image="https://cdn.pixabay.com/photo/2018/03/27/21/43/startup-3267505_960_720.jpg" data-background-opacity="0.2"
-->

## Design & Deploy a Private Cloud

---

## Choosing the Right Infrastructure

- Compliance
- Cost
- Performance
- Scalability
- Security

Note:

- *Compliance:* Do you need to comply with any compliance requirements? Vendors such as VMware and Red Hat have certifications for various compliance requirements.
- *Cost:* How much are you willing to spend? What is the total cost of ownership (TCO) of the infrastructure? What is the return on investment (ROI)?
- *Performance:* What is the expected performance of the infrastructure? What is the expected performance of the applications running on the infrastructure?
- *Scalability:* How much can the infrastructure scale? How quickly can the infrastructure scale? How much does it cost to scale the infrastructure?
- *Security:* How secure is the infrastructure? How secure is the data? How secure are the applications running on the infrastructure? Do you need to operate in an air-gapped environment?

---

## Storage Options

- Traditional Storage Area Network (SAN)?
- Hyperconverged Infrastructure (HCI)?
- Software-defined Storage (SDS)?

Note:
- *Traditional Storage Area Network (SAN)*: SANs are primarily used to make storage devices, such as disk arrays and tape libraries, accessible to servers so that the devices appear as locally attached to the operating system.
  - Pros: SANs offer high performance, reliability, and fault tolerance. They are excellent for applications that require high-speed data access and block-level storage, such as databases.
  - Cons: SANs can be expensive and complex to manage. They may also lack the scalability and flexibility that some modern applications require.
- *Hyperconverged Infrastructure (HCI)*: HCI combines compute, storage, and networking into a single system. It's a software-defined solution that is designed to simplify the management of data centres by consolidating each of these components into a single unit.
  - Pros: HCI is easy to scale by simply adding more units. It simplifies management by offering a single solution for all infrastructure needs. It can also offer cost savings by reducing the need for separate storage, compute, and networking devices.
  - Cons: HCI can be less flexible than other solutions, as you have to scale all resources together, even if you only need more of one. It may also not offer the same level of performance as dedicated storage solutions for certain workloads. It is also difficult to maintain a separation of duties between storage and compute.
- *Software-defined Storage (SDS)*: The storage services are delivered as software and the underlying hardware can be industry standard servers.
  - Pros: SDS offers great flexibility and scalability. It allows for easy management and automation, and can reduce costs by enabling the use of commodity hardware.
  - Cons: As with any software-defined technology, SDS requires a certain level of expertise to manage effectively. The performance can also vary depending on the quality of the software, hardware and network used.

---

## Network Options

- Flat or hierarchical?
- Multi-site?
- Throughput? Latency?
- Redundancy? Failover?

Note:
- *Flat or hierarchical?*
  - Flat networks are simple, with all devices connected on a single layer. This design can reduce management complexity and hardware costs, as it typically requires fewer switches and routers. However, as the network grows, the flat architecture can lead to scalability issues. Since all devices are part of the same broadcast domain, network traffic can become congested. Flat networks also allows for easier lateral movement of malicious actors.
  - Hierarchical networks use multiple layers to segment network traffic. Commonly, a three-layer model is used: core, distribution, and access. The core layer is the backbone of the network, the distribution layer manages policy and routing, and the access layer is where end devices connect. Hierarchical design can provide better performance, scalability, and manageability at the cost of increased complexity and hardware costs.
- *Multi-site?* A multi-site network is a network that spans multiple physical locations. This might involve leased lines, MPLS (Multi-Protocol Label Switching), or VPN (Virtual Private Network) over the public internet. The inter-site connections must have sufficient bandwidth to handle the expected data traffic. You may need to plan for peak times or special events that could cause a surge in data transfer. Plan for disasters that could take a whole site offline. This might involve replicating critical data and applications at a secondary site, or it could involve cloud-based backup and recovery solutions.
- *Throughput? Latency?* This is a trade-off between performance and cost. A network with high throughput and low latency can offer better performance and reliability, but it can also be more expensive to implement and maintain. Careful consideration must be made for the expected performance of the storage fabrics and applications running on the network. In some cases, you may need to implement a dedicated storage network or adopt vendor-specific technologies such as InfiniBand, Omni-Path and/or RDMA. Care must also be taken to ensure that the network allows for the expected growth of the infrastructure.
- *Redundancy? Failover?* This is a trade-off between performance and reliability. A network with high redundancy and failover capabilities can offer better reliability, but it can also be more expensive to implement and maintain. Careful consideration must be made for the expected reliability of the storage fabrics and applications running on the network. In some cases, you may need to implement a dedicated storage network or adopt vendor-specific technologies such as InfiniBand, Omni-Path and/or RDMA. Care must also be taken to ensure that the network allows for the expected growth of the infrastructure.

---

## Compute Options

- Virtual Machines (VMs)?
- Containers?
- Bare Metal?

Note:
- *Virtual Machines (VMs)*: Supporting virtual machine is a classic use case for cloud computing. Virtual machines are isolated from each other and the underlying hardware, allowing for greater security and flexibility. They can be easily moved between physical servers, allowing for better resource utilisation. They can also be easily scaled up or down as needed. However, virtual machines can be less efficient than other solutions, as they require a hypervisor to run.
- *Containers*: Containers are a lightweight alternative to virtual machines. With the growth of Kubernetes, it has become easier to manage containerised applications at scale. If you decide to support solely containerised applications, you may be able to reduce the number of physical servers required. However, containers are not suitable for all applications. They are not as secure as virtual machines, as they share the same kernel. They are also not as flexible, as they cannot run different operating systems.
- *Bare Metal*: Bare metal servers are physical servers that are not virtualised. They can offer better performance than virtual machines or containers, as they do not require a hypervisor or kernel. They can also offer better security, as they do not share the same kernel as other servers. However, bare metal servers are less flexible and significantly more expensive than virtual machines or containers.
