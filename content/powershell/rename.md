---
title: Rename files
---

```ps1
get-childitem *.dat | foreach { rename-item $_ $_.Name.Replace("foo", "bar") }
```