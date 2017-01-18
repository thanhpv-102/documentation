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

Setup couchbase admin in web view a large document ( > 2.5KB )
--------------

```
//Edit file

/opt/couchbase/lib/ns_server/erlang/lib/ns_server/priv/public/js/document.js

// Change 2500 to new size
```