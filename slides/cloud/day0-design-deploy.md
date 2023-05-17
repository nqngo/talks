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
