---
title: Permission
---

#### Create user
```sql
CREATE USER <uuser> WITH PASSWORD = '<strong_password>'; 
```

#### Add user to role
```sql
ALTER ROLE <role> ADD MEMBER <user>;
```

#### Check permission on schema
```sql
SELECT 
	state_desc, permission_name, 'ON', class_desc, 
	SCHEMA_NAME(major_id), 'TO', USER_NAME(grantee_principal_id)
FROM sys.database_permissions AS Perm
JOIN sys.database_principals AS Prin
ON Perm.major_ID = Prin.principal_id AND class_desc = 'SCHEMA'
```