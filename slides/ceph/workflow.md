### How <span class="color-yellow-400">Read/Write</span> Works?

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

interface "Client" as Client1
interface "Client" as Client2

database "Host 1" {
    Node "OSD" as Node1
    Node "OSD" as Node2
    Node1 -[hidden]- Node2
}
database "Host 2" {
    Node "OSD" as Node4
    Node "OSD" as Node5
    Node4 -[hidden]- Node5
}

database "Host 3" {
    Node "OSD" as Node7
    Node "OSD" as Node8
    Node7 -[hidden]- Node8
}

Client1 -[hidden] Client2
Client1 ..> Node2: upload to\nsingle node
Client2 <-- Node1
Client2 <-- Node4
Client2 <-- Node7: download from\na multiple node
Node2 .> Node5
Node2 .> Node8: replicates
@enduml
```