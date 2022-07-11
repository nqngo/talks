### <span class="color-yellow-400">Storage Format Overview</storage>

Data can be organised and presented in different storage formats: each with their own capabilities and limitations.

1. _File storage_.
2. _Block storage_.
3. _Object storage_.

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
database "Block" as Vol1
database "Block" as Vol2
database "Block" as Vol3
interface Volume as LUN

Vol1 - Vol2
Vol2 - Vol3
Vol1 -- Vol3
System . LUN
LUN . Vol1

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

---

### <span class="color-yellow-500">Object Storage</storage>

- Flat structure in which files are broken into pieces and spread out among hardware.

```language-plantuml
@startmindmap
!theme crt-amber
skinparam roundCorner 15
skinparam backgroundColor transparent
skinparam componentStyle rectangle

*_ text.txt
** text_obj
*_ picnic.mp4
** picnic_obj
*_ rick_astley.mp3
** rick_obj
@endmindmap
```

- Data is broken into discrete units called objects and is kept in a single repository, instead of files in folders or as blocks on servers.

---

### <span class="color-yellow-500">Object Storage (Cont.)</storage>

- Cost efficient.
- Pay for what you use.
- Scale easily.
- Fast read.
- Slow write, objects can’t be modified, have to write the object completely at once.
- Have to write app to use the object storage API.
- Network interface: _AWS S3_, _Swift_.