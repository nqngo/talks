<!--
.slide: data-background-image="https://images.unsplash.com/photo-1515890922410-ae767899d6b3" data-background-opacity="0.1"
-->

### <span class="color-openstack-red">OpenStack</span> Components

<span class="color-openstack-red">OpenStack</span> is comprised of several components

![](https://docs.openstack.org/security-guide/_images/marketecture-diagram.png)

<small>_Source_: https://docs.openstack.org/security-guide</small>

---

- Let us follow a <span class="color-yellow-400">simple scenario</span>

We are developers at _ACME Co._ that need to deploy:
1. A standard `[webserver]`, connected to the public network. 
2. A `[db]` database, connected to `[webserver]` using a private network.

_ACME Co._ has access to a default, out-of-the-box <span class="color-openstack-red">OpenStack</span> deployment at `https://demo.com/dashboard`