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

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

actor DevOps
actor NewOps
cloud CodeRepository
artifact Config
database PasswordManager
cloud ChatPlatform
cloud Production
cloud Test

DevOps <-[dashed]-> ChatPlatform: SaaS
NewOps <-[dashed]-> ChatPlatform: SaaS
DevOps <-[dashed]-> PasswordManager: SaaS
PasswordManager -[dashed]-> NewOps: share

DevOps ---> CodeRepository : push
DevOps -[dashed]-> CodeRepository : manage ENV
CodeRepository -[dashed]-> Config : store
DevOps -[dashed]-> Test : manage ENV
DevOps -[dashed]-> Production : manage ENV
Config -[dashed]-> Test: test
Config -[dashed]-> Production : apply 
```

Note:
This diagram presents an example workflow for a typical team.
---
```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

folder DevOps {
    actor Person
    interface PGP
}

cloud CodeRepository
artifact Config
artifact Secrets
cloud ChatPlatform
cloud Production
cloud Test

Person <-[dashed]r--> ChatPlatform: SaaS
PGP <-> Person

DevOps -d-> CodeRepository : push
CodeRepository -[dashed]r-> Config : store
CodeRepository -[dashed]r-> Secrets : store
Config -[dashed]-> Test
Config -[dashed]-> Production 
Secrets -[dashed]-> Test
Secrets -[dashed]-> Production
```
Note:
This diagram presents an ideal workflow to PGP key.
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