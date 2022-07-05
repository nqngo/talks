### <span class="color-openstack-red">OpenStack</span> Computing Service

![](https://openstack-xenserver.readthedocs.io/en/latest/_images/page25-launch-instance.png)

---

- [Nova](https://docs.openstack.org/nova/latest/) is used to manage compute instances.
- Back to our <span class="color-yellow-400">scenario</span>, to launch an compute instance, we required:
1. An <span class="color-yellow-400">availability zone</span>.
2. The instance <span class="color-yellow-400">name</span>.
3. The <span class="color-yellow-400">Flavor</span>.
4. <span class="color-yellow-400">Boot Source</span>.
5. A <span class="color-yellow-400">Keypair</span>.
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

### <span class="color-yellow-400">Boot Source</span>

- Boot from an <span class="color-yellow-400">_image_</span>: <span class="color-yellow-400">**Glance**</span>
- Boot instance from <span class="color-yellow-400">_volume_</span>: <span class="color-yellow-400">**Cinder**</span>
- Boot from an existing <span class="color-yellow-400">_snapshot_</span>.

---

### <span class="color-yellow-400">Keypair</span>

A **_ssh_** key that can be injected into a server **on launch**.
- Can be generated on the <span class="color-yellow-400">dashboard</span>.
- Or imported from your existing **SSH keys**.
- Imported keypair can have multiple public keys:
```
ssh-rsa AAAAB3NzaC1... user1@example.com
ssh-rsa AAAAB3NzaC1... user2@example.com
ssh-rsa AAAAB3NzaC1... user3@example.com
```

---

### <span class="color-yellow-400">Security Group</span>

_Named collection_ of simple network access rules to limit the types of traffic that access the <span class="color-yellow-400">_instances_</span>.
- Limit by _source of traffic_.
- Limit by _protocol_.
- Limit by _destination port_.

---

### <span class="color-yellow-400">Networking</span>

- Managed by <span class="color-yellow-400">_Neutron_</span>.
- Most cloud providers have a default network that NAT to the internet.
- Depends on implementation, private network can spanned multiple AZ.

---

### Back to our <span class="color-yellow-400">Example Scenario</span>

---

### <span class="color-yellow-400">Snapshot</span>

A mechanism that allows you to create a new _image_ from a _running instance_. Use Case:
1. As a backup mechanism.
2. As a templating mechanism.

_Live snapshot_ may be <span class="color-yellow-400">inconsistent</span>.

Most Openstack Nova deployment relies on QEMU to manage the VMs. **_qemu_guest_agent_** can be enforced consistency in _live snapshot_.

---

### <span class="color-yellow-400">Snapshot (Cont.)</span>

However, the instance or base image must be tagged with the property:
```
hw_qemu_guest_agent=yes
```
<img src="https://blog.ovhcloud.com/wp-content/uploads/2020/02/1AFD8AED-20D0-4ECE-8894-3EEA72649D0D.jpeg" width="50%">
<small>Source: [ovhcloud blog](https://blog.ovhcloud.com/create-and-use-openstack-snapshots/)</small>

---

### <span class="color-yellow-400">Migration</span>

An instance can be moved between compute hosts. Nova has multiple mechanisms:

1. _Live migration_: VM continues to run. Might fail if hosts have different configuration or versions.
2. _Cold migration_: VM shutoffs and relaunches on a new host. No change in flavor.
3. _Resize_: VM shutoffs and relaunches on a new host. Flavor will be changed.
4. _Rebuild_: VM shutoffs and relaunches on the same host. No change in flavor.