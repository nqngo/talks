### <span class="color-openstack-red">Swift</span> Architectural Overview



```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

interface "Client" as Client1
interface "Client" as Client2

queue "Load Balancer" as LB

rectangle "swift-proxy" as Proxy1
rectangle "swift-proxy" as Proxy2
rectangle "swift-proxy" as Proxy3


Client1 --> LB: upload to\nmultiple nodes
Client2 <.. LB: download from\na single node

LB -[hidden]- Proxy1
LB --> Proxy2
LB <.. Proxy3

database "Zone 1" {
    Node "Storage\n Node" as Node1
    Node "Storage\n Node" as Node2
    Node1 -[hidden]- Node2
}
database "Zone 2" {
    Node "Storage\n Node" as Node4
    Node "Storage\n Node" as Node5
    Node4 -[hidden]- Node5
}

database "Zone 3" {
    Node "Storage\n Node" as Node7
    Node "Storage\n Node" as Node8
    Node7 -[hidden]- Node8
}

Node1 -[hidden] Node4
Node4 -[hidden] Node7

Proxy1 -[hidden]- Node1
Proxy2 --> Node4
Proxy3 <.. Node7
Proxy2 --> Node2
Proxy2 --> Node8
@enduml
```