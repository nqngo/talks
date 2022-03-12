<!--
.slide: data-background-image="https://images.unsplash.com/photo-1582139329536-e7284fece509" data-background-opacity="0.3"
-->
# <span class="color-yubico-green">OpenPGP</span>

<small>Linux Unleased</small>

---

### Summary

- The only widely available OpenPGP card on the market.
- Created by [Phil Zimmermann](https://en.wikipedia.org/wiki/Phil_Zimmermann) in 1991 to securely uses BBSs, store messages and files for anti-nuclear activitists.
- [Web of trust](https://en.wikipedia.org/wiki/Web_of_trust) system vs. centralised model in PKI.
- Use for encryption, decryption, signing and authentication.
- No centralised infrastructure to setup.
- [How to setup your Yubikey OpenPGP mode](https://github.com/behindtheclouds/presentations/wiki/Setup-Yubikey-OpenPGP).
- PGP (Commercial) vs. GPG (Open source).

---

### Use Case: <span class="color-yellow-400">System Login</span>

`ssh-agent` prevents you from copying your keys to multiple remote hosts.

```shell
❯ ls .ssh/
authorized_keys  id_rsa  known_hosts
❯ eval `ssh-agent`
Agent pid 27624
❯ ssh-add .ssh/id_rsa
Identity added: .ssh/id_rsa (.ssh/id_rsa)
❯ ssh-add -l
2048 SHA256:BC9oVgKX/LuMr2WCkW230ZX... .ssh/id_rsa (RSA)
❯ ssh -A alice
...
alice:~$ ssh-add -l
2048 SHA256:BC9oVgKX/LuMr2WCkW230ZX... .ssh/id_rsa (RSA)
alice:~$ ssh brunhilde
```

If your `id_rsa` got compromised. You have no visibility on when your key is being used.

---

### Use Case: <span class="color-yellow-400">System Login</span>

Yubikey OpenPGP key cannot be taken off the device.

```shell
❯ cat .gnupg/gpg-agent.conf
use-standard-socket
enable-ssh-support
❯ cat .ssh/config
Match host * exec "gpg-connect-agent updatestartuptty /bye"
...
❯ ssh-add -l
256 SHA256:huflWm3hR... cardno:15 XXX XXX (ED25519)
❯ ssh -A alice
...
alice:~$ ssh-add -l
256 SHA256:huflWm3hR... cardno:15 XXX XXX (ED25519)
alice:~$ ssh brunhilde
```

Can add *touch* requirement on read for extra security.

---

### Use Case: <span class="color-yellow-400">Secret Management</span>

Even with CLI, password retrieval can be cumbersome.

```shell
❯ eval $(op signin)
Enter the password for nhat@main.com at mainexample.1password.com:
❯ op get item psql --vault cloudinfra-staging --fields password
AnOBvi0uSlYBaDP4Ssw0rD
```

---

### Use Case: <span class="color-yellow-400">Secret Management</span>

[`pass`](https://www.passwordstore.org/) can use GPG to store your secrets.
```shell
❯ pass
Password Store
├── cloudinfra-staging
│   └── psql_password
├── offboard.sh
└── onboard.sh
❯ cat .password-store/.gpg-id
nhat@main.com
nhat@backup.com
❯ pass git status
On branch main
nothing to commit, working tree clean
❯ pass show onboard.sh
export ONBOARD_PAGERDUTY_API_KEY=AnOBvi0uSlYBaD4PIK3y
❯ eval `$(pass show onboard.sh)`
```

---

### Use Case: <span class="color-yellow-400">Secret Management</span>

GPG integrates well with secret management in configuration management platform.

- [Puppet Secret management with Hiera-eyaml](https://puppet.com/docs/puppet/6/securing-sensitive-data.html#securing_sensitive_data-hiera-eyaml).
- [Ansible password-store lookup](https://docs.ansible.com/ansible/latest/collections/community/general/passwordstore_lookup.html).
- [Managing Kubernetes Secrets with Mozilla SOPS](https://www.thorsten-hans.com/encrypt-your-kubernetes-secrets-with-mozilla-sops/).

---

### Use Case: <span class="color-yellow-400">Encrypted Communication</span>

- OpenPGP is used for encrypted [email communication](https://support.mozilla.org/en-US/kb/digitally-signing-and-encrypting-messages) ie. *Edward Snowden*.
- Can be use as impropertu secret sharing over chat.

```plaintext
H: Hey N, what is the office's wifi password?
N: Sure, put this in an wifi.asc file and run 'gpg wifi.asc'
...
hF4D/HqlEBDXF8kSAQdAgWxdWa6ZF0kZ7mJfljO723QnF8KUOtIR8dloiwszagkw
r+BAodbnQpBtTL5ukDaRge2QT/8w3Slow3GHkPQ7kWMREU17ORGvdnQOUEgD8+Te
0sAIAYMStXOPp//66KBFwzYA9vsa4X3GFVPFNEsnVSywLkvZKbPmxmqltXtqAkmm
...
```

---

### Use Case: <span class="color-yellow-400">Digital Signature</span>

[Sign git commit](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work) to verify yourself:

```shell
❯ git commit -S
❯ git log --show-signature
commit 5ff2005417bd160535... (HEAD -> main, origin/main)
gpg: Signature made Sun Mar  6 14:12:33 2022 AEDT
gpg:                using EDDSA key 4C2DE23A1...
gpg:                issuer "nhat@..."
gpg: Good signature from "Nhat Ngo <nhat@..." [ultimate]
Author: Nhat Ngo <nhat@...>
Date:   Sun Mar 6 14:11:56 2022 +1100

    Add enterprise and team slide decks for Yubikey.
    
    Rename gpg slide to pgp.
```
![](https://user-images.githubusercontent.com/300046/116947094-1d52a180-ac39-11eb-99c0-a76e793f0b8e.png)

---

### Use Case: <span class="color-yellow-400">Digital Signature</span>

GPG can also be used to [make and verify file signatures](https://www.gnupg.org/gph/en/manual/x135.html).

```shell
❯ cat testdoc.txt
Hi this is a test doc!
❯ gpg --clearsign testdoc.txt
❯ cat testdoc.txt.asc
 -----BEGIN PGP SIGNED MESSAGE-----
 Hash: SHA256
 Hi this is a test doc!
 -----BEGIN PGP SIGNATURE-----
 iHUEARY...
 -----END PGP SIGNATURE-----
 ❯ gpg --verify testdoc.txt.asc
gpg: Signature made Tue Mar  8 21:22:59 2022 AEDT
gpg:                using EDDSA key 502843279...
gpg: Good signature from "Nhat Ngo <nhat.ngo@...>"
```

---

### Discussion Points

- Intimidating to get started.
- GPG supports can be lacking.
- No need to run any infrastructure.
- Excellent integration to CLI workflow.