### <span class="color-yellow-400">Monitoring Cluster Health</span>

- `swift-dispersion-report`: measure the overall cluster health. It does so by ensuring that the various replicas of an object and container
are in their proper places.
- `swift-recon`: retrieve various metrics and telemetry information about a cluster that has been collected by the `swift-recon` middleware.

---

### <span class="color-yellow-400">Dead Disk in Swift</span>

- Must either be swapped relatively quickly or remove from the ring.
- Otherwise, all _partitions_ on the disk are not automatically moved.

---

### <span class="color-yellow-400">Rebooting a Storage Node</span>

- Data not moving automatically.
- If a storage node needs reboot, simply reboot it.