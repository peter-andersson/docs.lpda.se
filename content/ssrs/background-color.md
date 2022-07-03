---
title: Background color
---

#### Alternate background color
##### Using row number
```
=IIF(RowNumber(Nothing) Mod 2 = 0, "#eeeeee","#ffffff")
```

```
=IIF(RunningValue(Fields!Field1.Value & "" & Fields!Field1.VALUE, COUNTDISTINCT, NOTHING) MOD 2 = 0, "#eeeeee","#ffffff")
```

##### Using distinct on group
```
=IIF(RunningValue(Fields!Field.Value, CountDistinct, Nothing) MOD 2, "#eeeeee", "#ffffff")
```