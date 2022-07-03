---
title: Locked tables
---

```sql
SELECT * FROM sys.dm_tran_locks
  WHERE resource_database_id = DB_ID()
  AND resource_associated_entity_id = OBJECT_ID(N'Tabellnamn');
```