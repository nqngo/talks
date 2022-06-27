### <span class="color-openstack-red">OpenStack</span> Identity Service

![](https://docs.openstack.org/horizon/latest/_images/dashboard_identity_tab.png)

---

- [Keystone](https://docs.openstack.org/keystone/latest/) is the _identity management component_.
- <span class="color-yellow-500">Keystone</span> is used for _authentication_ and _high-level authorisation_.
- <span class="color-yellow-400">Keystone</span> is greatly simplified from [AWS IAM](https://aws.amazon.com/iam/).
- You log in as a <span class="color-yellow-400">User</span>.
- `Application Credentials` can be used for limited access or scripting.


---

### <span class="color-yellow-400">Users</span> 
- Can belong to multiple <span class="color-yellow-400">Projects  (_tenants_)</span>.
- A <span class="color-yellow-400">User</span> can have multiple <span class="color-yellow-400">Roles</span> in a <span class="color-yellow-400">Project</span>.

---

### <span class="color-yellow-400">Projects</span> 

- All resources are managed per <span class="color-yellow-400">Projects</span>.
- <span class="color-yellow-400">Projects</span> have <span class="color-yellow-400">Quotas</span> as defined in the `Overview` screen.

---

### <span class="color-yellow-400">Roles</span> 

- <span class="color-yellow-400">Roles</span> have to be mapped to an authorisation policy config on the backend.
- Can have `reader` role for read only access.
- Can have `ResellerAdmin` role to performance administration on sub-projects.

