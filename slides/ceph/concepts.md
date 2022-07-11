### <span class="color-yellow-400">Core Ceph Concepts</span>

- _Pools_
- _Placement Groups (PGs)_
- _CRUSH (deterministic, decentralised placement algorithm)_

---

### <span class="color-yellow-400">Pools</span>

- Logical container for storage objects
- Have a set of parameters:
  - Name, ID
  - Number of replicas or erasure coding settings
  - Number of placement groups
  - CRUSH rules
  - Owner
- Support:
  - Create/read/write objects
  - Snapshot

---

### <span class="color-yellow-400">Placement Groups (PGs)</span>

- Tracking object on a per-object basis is computationally expensive.

![](https://docs.ceph.com/en/latest/_images/ditaa-a53f413321ac943aa924fb6b58c0b3716821f6a7.png)
- A PG tracks mutliple objects, think **postcode**.

---
### <span class="color-yellow-400">Placement Groups (PGs)</span>

- Help balance data across OSDs.
- One PG typically spans several OSDs.
- One OSD typically serves many PGs.
- **Tunable**! Basic rule of thumb is 50-100 per OSD.

---
### <span class="color-yellow-400">CRUSH</span>

- [_Controlled Replication Under Scalable Hashing_](https://ceph.com/assets/pdfs/weil-crush-sc06.pdf).
- CRUSH map consists of a hierarchy that describes the physical topology (row, rack, host).
- Rules for which OSDs to consider for certain pool/PGs.
- Deterministic and maintained by `ceph-mon`s.
- **Clients understand CRUSH** and communicate with OSDs directly. This is the magic that removes bottlenecks.

---

### <span class="color-yellow-400">Replication Pool</span>

- _n_ exact full-size copies
- Increase read performance (striping)
- More copies lower throughput
- Increased cluster network utilisation for writes
- Rebuilds leverage multiple sources
- Significant capacity impact

---

### <span class="color-yellow-400">Erasure Coding Pool</span>

- Data split into _k_ parts plus _m_ redundancy codes
- Better space efficiency
- Higher CPU overhead
- Significant CPU & cluster network impact, especially during rebuild
- Cannot directly be used with block devices
