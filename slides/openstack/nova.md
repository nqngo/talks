### <span class="color-openstack-red">OpenStack</span> Computing Service

![](https://www.linuxtechi.com/wp-content/uploads/2016/01/Instances-Details-OpenStack-Dashboard-1024x540.jpg)

---

- [Nova](https://docs.openstack.org/nova/latest/) is used to manage compute instances.
- Back to our <span class="color-yellow-400">scenario</span>, to launch an compute instance, we required:
1. An <span class="color-yellow-400">availability zone</span>.
2. The instance <span class="color-yellow-400">name</span>.
3. The <span class="color-yellow-400">Flavor</span>.
4. <span class="color-yellow-400">Boot Source</span>.
5. A <span class="color-yellow-400">Key Pair</span>.
6. <span class="color-yellow-400">Security Group</span>.
7. <span class="color-yellow-400">Networking</span>.

---

### <span class="color-yellow-400">Availability Zone</span>

- _Logical abstraction_ for partitioning a cloud.
- Partition a cloud on arbitrary factors: such as _location (country, datacenter, rack)_, _network layout_ or _power source_.
- Should not be assumed to map to fault domains and provide no intrinsic HA benefit.
- Defined by the _cloud providers_.

---

### <span class="color-yellow-400">Flavor</span>

- Define the _compute_, _memory_, and _storage capacity_ of computing instances.
- To put it simply, a flavor is an _available hardware configuration_ for a server.
- Flavor specs:
  1. _VCPUs_: Number of virtual CPUs.
  2. _Memory_: RAM.
  3. _Root Disk_: Disk space for `root (/)` partition.
  4. _Ephemeral Disk_: Disk space for the _ephemeral partition_. When a VM is terminated, all data on the ephemeral disk is lost. Ephemeral disks are not included in any <span class="color-yellow-400">snapshots</span>.

---

