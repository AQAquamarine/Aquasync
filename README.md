AQSynchronization
=================

AQSynchronization is an iOS data synchronization framework / protocol and is a subproject of [Aquamarine iOS Model Framework](https://github.com/kaiinui/Aquamarine).

Protocol
---

Additional columns added to objects to handle synchronization.

|column name   |type     |presence |origin |description|
|--------------|---------|---------|-------|-----------|
|gid           |GUID     |global   |local  |generated locally when object created|
|UST           |Timestamp|remote   |remote |time when the data get merged to the master|
|deviceToken   |GUID     |global   |local  |notate which device is the origin of the data|
|isDirty       |boolean  |local    |local  |true when modified/created|
|localTimestamp|Timestamp|global   |local  |time when last modified|
|deletedAt     |DateTime |global   |local  |for soft deletion|

- master: Master database (backend)
- UST: Update Sequence Timestamp

Synchronization Sequence
---

1. pullSync (pulls modifications from master database)
2. pushSync (pushes modification which occured on local to master database)

Built on
--

[EDQueue](https://github.com/thisandagain/queue)
[Realm](https://github.com/realm/realm-cocoa)

Related Projects
---

- [Aquamarine](https://github.com/kaiinui/Aquamarine) (AQSynchronization is a subproject of Aquamarine project)

References
---

[Evernote Synchronization via EDAM](https://dev.evernote.com/media/pdf/edam-sync.pdf)
