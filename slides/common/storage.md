### <span class="color-yellow-400">Storage Format Overview</storage>

Data can be organised and presented in different storage formats: each with their own capabilities and limitations.

1. _File storage_.
2. _Block storage_.
3. <span class="color-yellow-500">_Object storage_</span>.

---

### <span class="color-yellow-500">File Storage</storage>

- Data is stored as a single piece of information inside a folder.

```language-plantuml
@startmindmap
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

* root
** home
*** user1
**** projects
****_ text.txt
****_ password.txt
*** user2
** etc
*** program1
*** ...

@endmindmap
```

- Required limited _metadata_ to know where the file is kept.
- Oldest and most widely used storage format.

---

### <span class="color-yellow-500">File Storage (Cont.)</storage>

- Constrained by a single path to the data.
- Required common file-level protocol.
- Scale by building new systems, not add more capacity.
- Simple to configure.
- Good performance over LAN.
- Support _file sharing_, _global file locking_.
- Network inteface: _NFS_, _SMB_, _NTFS_, _CephFS_.

---

### <span class="color-yellow-500">Block Storage</storage>

- Block storage chops data into blocks and stores them as separate pieces.

```language-plantuml
@startuml
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

agent System
database "Volume" as Vol1
database "Volume" as Vol2
database "Volume" as Vol3

Vol3 . System
System - Vol1
System - Vol2

@enduml
```

- Each block of data is given a _unique identifier_.
- Storage system place the smaller pieces of data wherever is most convenient.

---

### <span class="color-yellow-500">Block Storage (Cont.)</storage>

- Decouple the data from the user’s environment.
- Creates multiple paths to the data and allows the user to retrieve it quickly.
- Low latency.
- Best of structured data.
- Network interface: _direct attached_, _iSCI_, _RBD_, _Cinder_.

