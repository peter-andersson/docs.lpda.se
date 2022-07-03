---
title: Timezone
---

#### Timestamp for timezone
Get the current time for a specific timezone

```sql
CAST(CURRENT_TIMESTAMP AT TIME ZONE 'UTC' AT TIME ZONE 'Central European Standard Time' AS DATETIME)
```