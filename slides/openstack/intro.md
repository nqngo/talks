_<span class="background-1990">For Aeons Past...</span>_

On-premise computing was the only offering for companies.

Software is installed and configured locally on a company’s servers.

_However..._
---

1. Capacity management is a huge cost investment.

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle
skinparam linetype ortho

State Business
State Architect
State DataCenter
State Sysadmins

Business -right-> Architect
Architect -right-> DataCenter
DataCenter -right-> Sysadmins
Sysadmins -left-> Business

Business: - Identify business requirements
Business: - Identify personnel required

Architect: - Purchase required hardwares
Architect: - Identify DC constraints (power, space, cooling)

DataCenter: - Setup, install, test servers
DataCenter: - Update DC constraints

Sysadmins: - Setup softwares
Sysadmins: - Identify changes to business requirements
@enduml
```

2. Company is unable to scale _on-demand_.
3. Softwares usually compiled to match deployed hardwares.
4. Deployment is managed centrally by sysadmins.
5. _Disaster recovery_ or _redundancies_ have to be planned during the design.
6. Telecommunication advancements make it possible to remote computing resources
as a commodity.
---

<!--
.slide: data-background-image="https://images.unsplash.com/photo-1554921027-b91f0beeb07d" data-background-opacity="0.2"
-->

_In 2006_, <span class="color-yellow-400">AWS</span> introduced S3 (object storage) and EC2 (virtualised compute), pioneer the on-demand IaaS.

_In 2008_, <span class="color-yellow-500">Google</span> introduced Google App Engine.

_In 2010_, <span class="color-openstack-red">Openstack</span> started as a joint project of _Rackspace Hosting_ and _NASA_.

_In 2010_, <span class="color-yellow-500">Microsoft</span> launches Azure.

_From 2012_,<span class="color-openstack-red">Openstack</span> is managed by _OpenStack Foundation_ as _free, openstandard_ cloud flatform.

---

# Why <span class="color-openstack-red">Cloud?</span>

1. _More efficient usage of resources_: virtualisation enables sharing of physical services. Cloud platform also enables multi-tenancy, allowing developers to manage their own infrastructures.
2. _High scalability_: Provision of services based on _current demand requirements_. Dynamic provisioning can be done using automation for dynamic scaling.

---

## Why <span class="color-openstack-red">Openstack?</span>

1. **Free**.
2. **Open standard**.
3. Easily customised with required services to suit business needs.
4. Interoperatable.
5. Vibrant commerical ecosystems.
6. Open-sourced codebase allowing auditing and security vulnerabilities mitigation.
