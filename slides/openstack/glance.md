### <span class="color-openstack-red">OpenStack</span> Image Service

![](https://docs.openstack.org/horizon/latest/_images/create_image.png)

---

- [Glance](https://docs.openstack.org/glance/latest/) is the service that stores, manage, and shares _immutable_ disk image for other <span class="color-openstack-red">OpenStack</span> services.
- A <span class="color-yellow-400">compute instance snapshot</span> is a Glance image.
- Images can be shared between projects.
- Images can be downloaded and launched on your local hypervisors.
- Local images can be uploaded and run on the cloud, providing it has the required _VirtIO drivers_ and _cloud-init_.

---

A <span class="color-yellow-400">Glance Image</span> is:
- Immutable
- Atomic