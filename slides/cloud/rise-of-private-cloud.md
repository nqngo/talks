## Traditional Ops

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle
skinparam linetype ortho

State Business
State Sysadmins
State Developers

Business -right-> Developers
Developers -right-> Sysadmins
Sysadmins -left-> Business

Business: - Give requirements
Business: - Provide funding
Developers: - Write softwares
Developers: - Fix bugs
Sysadmins: - Install softwares
Sysadmins: - Monitor resources
@enduml
```

1. Company is unable to scale _on-demand_.
2. Developers have little visibility on the actual operation loads.
3. Deployment and upgrade are managed centrally by sysadmins.
4. Bug fixes are slow because of static cycle.
