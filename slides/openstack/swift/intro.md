### What is <span class="color-openstack-red">OpenStack Swift?</span>

<span class="color-openstack-red">Swift</span> is a <span class="color-yellow-400">_highly available_</span>, <span class="color-yellow-500">_distributed_</span>, <span class="color-yellow-400">_eventually consistent_</span> <span class="color-yellow-500">_object store_</span>.

For <span class="color-openstack-red">Swift</span> introduction from user's perspective, refer the to accompanied talk:

[Introduction to Openstack (2022)](https://talks.nhat.ngo.cx/2022-openstack-intro)

---

### <span class="color-yellow-400">Object Storage</span>

- Scalability.
- Pay as you go.
- Mix and match commodity hardware.
- Object immutability.
- Works well with high latency network (over WAN).

---

### <span class="color-yellow-400">Eventually Consistent</span>

- Suppose a container server is under load and a new object is put in to the system.
- Object will be available for reads as soon as the proxy server responds  with success.
- However, the container server did not update the object listing.
- Container listings, therefore, may not immediately contain the object.

---

### <span class="color-yellow-400">Distributed</span>

- Swift cluster can span multiple <span class="color-yellow-500">Regions</span>.
- A <span class="color-yellow-500">Region</span> can have multiple <span class="color-yellow-500">Zones</span>.

---

### <span class="color-yellow-400">Highly Available</span>

- Multiple proxy servers can be deployed and requests are load-balanced between them.
- Each proxy server instance is stateless and able to respond to requests for the entire cluster.