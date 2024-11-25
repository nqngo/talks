## <span class="color-yellow-400">Hyperstack Terraform Provider</span>

---

To get started with the Hyperstack Terraform provider, you need to install Terraform and the Hyperstack provider plugin.

---

Instruction is available in our Confluence for EARLY ACCESS.

[EARLY ACCESS Hyperstack Terraform Provider](https://nexgencloud.atlassian.net/wiki/spaces/HK/pages/530972673/EARLY+ACCESS+Hyperstack+Terraform+Provider)

---

```hcl
# Create a CANADA-1 environment
resource "hyperstack_core_environment" "canada" {
  name   = "canada1-region"
  region = "CANADA-1"
}

# Create a VM with 1x RTX-A6000 GPU
resource "hyperstack_core_virtual_machine" "my_test_vm" {
  name               = "my-canada-test-vm"
  environment_name   = hyperstack_core_environment.canada.name
  key_name           = "my-ssh-key"
  image_name         = "Ubuntu Server 22.04 LTS R535 CUDA 12.2"
  flavor_name        = "n3-RTX-A6000x1"
  user_data          = ""
  assign_floating_ip = true
}
# Allow port 22 to SSH into this machine
resource "hyperstack_core_virtual_machine_sg_rule" "ssh_access" {
  virtual_machine_id = hyperstack_core_virtual_machine.my_test_vm.id
  direction        = "ingress"
  ethertype        = "IPv4"
  port_range_min   = 22
  port_range_max   = 22
  protocol         = "tcp"
  remote_ip_prefix = "0.0.0.0/0"
}
```

---

## <span class="color-yellow-400">Use Cases</span>

---

- Internal development environments
- Sales demos
- Training environments & labs
- CI/CD pipelines
- Spin up Kubernetes clusters

