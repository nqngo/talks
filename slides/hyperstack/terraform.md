## <span class="color-yellow-400">Terraform</span>

---

- Industry vendor-neutral Infrastructure as Code (IaC) choice
- Declarative configuration language
- Version control friendly
- Supports multiple cloud providers

---

## <span class="color-yellow-400">Example</span>

---

Spinning up an instance in AWS

```hcl
provider "aws" {
  region = "us-west-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}

output "ip" {
  value = aws_instance.example.public_ip
}
```

---

```bash
# Initialize the provider
$ terraform init

# Preview the changes
$ terraform plan

# Apply the configuration to create the VM.
$ terraform apply 
```