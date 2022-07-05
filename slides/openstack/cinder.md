### <span class="color-openstack-red">OpenStack</span> Block Storage

![](https://ibm-blue-box-help.github.io/help-documentation/img/en/create_volume.png)

---

- [Cinder](https://docs.openstack.org/cinder/latest/) is the OpenStack Block Storage service.
- Providing _persistent volumes_ to **Nova** virtual machines, **Ironic** bare metal hosts, containers,...
- Analogous to a virtual hard drive.
- Launching a volume requires:
1. <span class="color-yellow-400">Volume Source<span>
2. <span class="color-yellow-400">Type</span>
3. <span class="color-yellow-400">Size</span>: The size of volume in gibibytes (GiB).
4. <span class="color-yellow-400">Availability Zone</span>
---

### <span class="color-yellow-400">Volume Source</span>

- _No source, empty volume_: Creates an empty volume with no file system or partition table.
- _From a snapshot_: Use a <span class="color-yellow-400">volume snapshot</span> as source.
- _From an image_: Use <span class="color-yellow-400">Glance image</span> as source.
- _From another volume_: Use an existing volume as source.

---

### <span class="color-yellow-400">Volume Type</span>

- Depends on the cloud providers' implementation.
- Usually use to differentiate between different hardware backend: SSDs vs HDDs.

---

### <span class="color-yellow-400">Availability Zone</span>

- Configured by the cloud providers.
- Usually match the _Nova availability zone_.

---

### Back to our <span class="color-yellow-400">Example Scenario</span>

---

### <span class="color-yellow-400">Using an empty volume</span>

- Mount the created volume to the instance.
- Format the volume like a new hard drive.
- Create a file system on the attached drive.

---

### <span class="color-yellow-400">Volume Snapshot</span>

- Similar concept to <span class="color-yellow-400">instance snapshot</span>.
- Use backend implementation and might create dependencies chain.
- Usually fast by ultilising backend snapshot capability.
- _Immutable_ but _not atomic_.
- Snapshot stores in <span class="color-yellow-400">Cinder backend</span>.

---

### <span class="color-yellow-400">Volume Backup</span>

- Volume backup can only be restored to the _same volume_.
- Usually configured to backup to <span class="color-yellow-400">Swift</span>.
- Slow as it needs to change storage backend.
- _Immutable_ but _not atomic_.