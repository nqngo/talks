<!--
.slide: data-background-image="https://images.unsplash.com/photo-1522071820081-009f0129c71c" data-background-opacity="0.2"
-->

# Team Usage

<span class="color-yubico-green">Yubikeys</span> fit in a team environment
<!--.small-->

---

### Experience Point

- University of Melbourne adopted Yubikeys for cloud devops team.
- No central authority dictates each team choice of security enhancements.
- Natural fit because we are collaborating with [Nectar Cloud](https://dashboard.rc.nectar.org.au) federation.
- Small team of under 20 people.
- OpenPGP for developers, U2F for SaaS and other interfaces.

---

### Experience Point

- Ordering directly from [Yubico](https://www.yubico.com/au/store/) to avoid supply chain attack.
- Security specialist [create the OpenPGP keys](https://github.com/behindtheclouds/presentations/wiki/Setup-Yubikey-OpenPGP) to avoid backup private key.
- Key expiry are staggered so that all keys do not expire at the same day and lock everyone out.
- DevOps finalise the setup on their own workstation.
- 2 keys each for backup.

---

### Experience Point

- A central `password-store` is commited to `git` and socialise amongst the team.
- DevOps team key must in the shared public GPG key registry.
- Software GPG key is owned only by the CI/CD automation.
- Secrets are re-encrypt once team members leave or join.