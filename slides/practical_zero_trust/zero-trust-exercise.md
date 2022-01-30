<h3><span class="color-yellow-400">Ops Session:</span> <span class="color-yellow-500 background-1990"> business</span> scenario</h3>

- *LaserCo.* is a laser cutting business.
- Produced a winning laser quoting app.
- Large revenue from B2B.
- Big investment in IT infrastructures & staffs.
- COVID-19 causes staffs shortage & requires remote working.
- Your task: improve security posture of the company.

---

<h3><span class="color-yellow-400">Ops Session:</span> IT Components</h3>

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

actor "Dev"
actor "Staff"

cloud "WAN" as WAN

cloud "SAAS" as SAAS {

    component "One Drive"
    component "MS Exchange"
}

cloud "CLOUD" as CLD {
    [WWW] <<Wordpress>>
    [QuotingApp] <<Python>>
    database "DB-as-a-Service" as REMDB
}

cloud "LAN" as LAN {

    together {
        [Billing] <<PHP>>
        [Quoting] <<Java>>
        database "DB" as DB
    }
    together {
       
        [LaserMachine] <<Windows XP>>
        
        [DEV{1..3}] <<OSX>>
        [OFFICE{1..8}] <<Windows 10>>
    }

    together {
        [Chromecast]
        [SmartTV]
        [PRINT{1..3}]
        [NVR]
        [CAM{1..10}]
    }

}

Dev ~d~> [DEV{1..3}]: RemoteDesktop
Staff ~d~> [OFFICE{1..8}]: RemoteDesktop

WAN <.d.> LAN : border firewall
WAN . SAAS
WAN .r.. [QuotingApp]
WAN .r.. [WWW]

[WWW] .. REMDB
[QuotingApp] .. REMDB

[OFFICE{1..8}] .d.> [SmartTV]
[DEV{1..3}] .d.> [SmartTV]
[LaserMachine] .[hidden]. [NVR]
[LaserMachine] .[hidden]. [CAM{1..10}]

[Billing] .d. DB
[Quoting] .d. DB
@enduml
```

---

<h3><span class="color-yellow-400">Ops Session:</span> Staff Complaints</h3>

1. Can't print remotely.
2. Too many passwords.
3. Password changes too regularly.
4. Almost suffer a ransomware attack.
5. Hard to share files.
6. Staff documents are lost when they quit.
7. Have to manually monitor if services are down.
8. Root SSH password login.
9. Source code is in a zip file.

<!-- ```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

cloud "WAN" as WAN

cloud "SAAS" as SAAS {

    component "One Drive"
    component "MS Exchange"
}

cloud "CLOUD" as CLD {
    [WWW] <<Wordpress>>
    [QuotingApp] <<TS>>
    database "DB-as-a-Service" as REMDB
}

cloud "LAN" as LAN {

    together {
        component "LegacyApp" as LEGAPP {
            [Billing] <<PHP>>
            [Quoting] <<Java>>
        }

        database "DB" as DB
    }
    together {
        component "LegacyHardware" as LEGHW {
            [LaserMachine] <<Windows XP>>
        }

        component "Hardware" as HW {
            [DEV{1..3}] <<OSX>>
            [OFFICE{1..8}] <<Windows 10>>
        }
    }

    together {
        component "IOT" as IOT{
            [Chromecast]
            [SmartTV]
        }

        component "Security" as SEC {
            [NVR]
            [Camera{1..10}]
        }
    }

}

WAN <.d.> LAN : border firewall
WAN . SAAS
WAN .r.. [QuotingApp]
WAN .r.. [WWW]

[WWW] .. REMDB
[QuotingApp] .. REMDB

[OFFICE{1..8}] .d.> [SmartTV]
[DEV{1..3}] .d.> [SmartTV]
LEGHW .[hidden]. SEC

[Billing] .d. DB
[Quoting] .d. DB
@enduml
``` -->