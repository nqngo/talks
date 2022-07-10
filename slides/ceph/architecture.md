### <span class="color-yellow-400">Ceph Architecture</span>

![](https://assets.ubuntu.com/v1/b05b5a3c-Ceph_diagrams-02.svg)

---

A minimal Ceph storage cluster consists of:

- <span class="color-yellow-400">_Monitors (ceph-mon):_</span> holds the map of the cluster state, active/failed nodes, cluster configuration, and data placement.
- <span class="color-yellow-400">_Managers (ceph-mgr):_</span> holds cluster metrics, dashboard, and interface to external monitoring.
- <span class="color-yellow-400">_Object storage devices (ceph-osd):_</span> store the actual data and handle replication, erasure coding, recovery, and rebalancing. Conceptually, an OSD is a slice of CPU/RAM and the underlying SSD/HDD.

---

In addition, to provide _object storage_ and _file storage_ capability:
- <span class="color-yellow-400">_Rados Gateways (ceph-rgw):_</span> provide object storage APIs (swift and S3) via http/https.
- <span class="color-yellow-400">_Metadata servers (ceph-mds):_</span> store metadata for the Ceph FS, mapping filenames and directories to RADOS objects and enabling the use of POSIX semantics.

---
### <span class="color-yellow-400">ceph-mon</span>

- The brain cells of the cluster.
- Cluster membership.
- _**Consensus**_ for distributed decision making.
- Do not serve stored objects to clients.
- Best to deploy in _odd number_.

---
### <span class="color-yellow-400">ceph-osd</span>

A Ceph OSD consists of 2 to 3 components:
- <span class="color-yellow-400">_Object Storage Daemon (OSD):_</span> handle replication, erasure coding, recovery, and rebalancing.
- <span class="color-yellow-400">_File system (FS):_</span> the file system (btrfs, xfs). No longer needed in _bluestore_.
- <span class="color-yellow-400">_Disk:_</span> The physical disk to store a data.

An OSD Node consists of multiple `ceph-osds`.
