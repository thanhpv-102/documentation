Backup all buckets, all node
----------------------------

```
cbbackup http://<host>:8091 ~/cbbackup/ -u <user> -p <password>
```

Restore backup
--------------

```
cbrestore ~/prodbak/ http://<user>:<password>@localhost:8091
```