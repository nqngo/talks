### <span class="color-openstack-red">OpenStack</span> Networking Service

---

- [Neutron](https://docs.openstack.org/neutron/latest/) is the service providing virtual networking.
- Allow the VMs to communicate with each other and external network.
- Apply security group on the virtual attached ports.
- (Optional) Load Balancer as a Service (LBaaS).
- (Optional) Firewall as a Service (FWaaS).
- (Optional) [VPN as a Service](https://docs.openstack.org/neutron-vpnaas/latest) (VPNaaS).

---

### <span class="color-yellow-400">Neutron Deployment Model</span>

- _Flat_: All instances reside on the same network, which can also be shared with the hosts.
- _Layer 2 (VLAN)_: Users to can create project networks using VLAN IDs that correspond to VLANs present in the physical network.
- _Overlay_: Encapsulated project traffics in a _GRE/VXLAN/GENEVE tunnel_ to traverse L3 networking or over the internet.

---

### <span class="color-yellow-400">Project Network</span>

- A project network can be created and managed by a project <span class="color-yellow-400">user</span>.
- A project network can create a virtual router to provide _DHCP_.
- Use Linux namespaces on the hypervisor node.
- Namespacing enable overlapping IP addresses for different projects.

---

### Back to our <span class="color-yellow-400">Example Scenario</span>

---

### <span class="color-yellow-400">Floating IP</span>

- Instance usually launches with a _private IP address_.
- Instance can also have a _public IP address_ that is reachable from the internet.
- However, this pool of public IPv4 is _usually highly limited_.

---

### <span class="color-yellow-400">Floating IP (Cont.)</span>
- These public IP addresses usually formed a <span class="color-yellow-400">Floating IP</span> pool that can be allocated and associated to a particular instance.
- One floating IP address per instance any given time.
- Floating IP can be diassociated and moved to another instance.

---

### <span class="color-yellow-400">LBaaS</span>

- Allow the project to configure multiple listener ports on a single load balancer IP address.
- **LBaaS v1**: introduced in Juno (deprecated in Liberty)
- **LBaaS v2**: implemented by another project [Octavia](https://docs.openstack.org/octavia/latest/)
- No migration path exists between v1 and v2 load balancers.

---

### <span class="color-yellow-400">FWaaS</span>

- Allow granular control over the network traffic than <span class="color-yellow-400">security group</span>.
- Most provider might not provide this optional functionality.
- At the time of writing, incompatible with upstream _OVN provider_.