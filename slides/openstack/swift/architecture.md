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

---

### <span class="color-openstack-red">Swift</span> Components

A minimal _Swift_ setup consists of the following:

- **_Proxy server:_** accepting requests from clients and proxying objects streamed from an object server. Also responsible for read/write quorum.
- **_Account server:_** tracks the names of _containers_ in a particular account and statistics. Data is stored in SQL databases.
- **_Container server:_** similar to the account server, except that it deals with object names in a particular container.
- **_Object server:_** Simply store objects.

---

### <span class="color-yellow-400">Logical organisation of objects</span>

Swift logically is pretty simple

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

rectangle "Account" {
    rectangle "Container" {
        (Object) as Obj1
        (Object) as Obj2
    }

    rectangle "Container " {
        (Object) as Obj3
    }
}
@enduml
```
- **_Account_:** A project in Keystone.
- **_Container_:** Logical grouping of files, think _flat directory_.
- **_Objects_:** Essentially _files_.

---

### <span class="color-yellow-400">Physical data organisation</span>

Swift classifies the location of data into a hierarchy

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

rectangle "Region" {
    database "Zone" as Zone1 {
        Node "Storage\n Node" as Node1 {
            (Device) as d1
            (Device) as d2
        }
        Node "Storage\n Node" as Node2 {
            (Device) as d3
        }
    }

    database "Zone" as Zone2 {
        Node "Storage\n Node" as Node3 {
            (Device) as d4
            (Device) as d5
        }
        Node "Storage\n Node" as Node4 {
            (Device) as d6
        }
    }
}
@enduml
```
---

### <span class="color-yellow-400">Physical data organisation</span>

- **_Region:_** geographically separated and can be over high-latency link.
- **_Zone:_** Set of storage nodes that share different availability characteristics (_buildings, power sources, network connections, rack_). Zones must be connected via low-latency links.
- **_Storage Server_:** Holds the physical disks.
- **_Device (Disk)_:**  Can physically be in the _Storage Server_ or via _JBOD_.

---

### <span class="color-yellow-400">Swift Ring</span>

- Swift uses a semi-static table to determine where to place objects and their replicas.
- It is semi-static because the look-up table, called a **_ring_**, is created by an external process called the `ring builder`.
- The ring can be modified, but not dynamically.
- It is not distributed, every storage node has a complete copy of the ring.