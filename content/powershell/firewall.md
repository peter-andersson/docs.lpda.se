---
title: Windows firewall
---

```ps1
Get-NetFirewallRule -DisplayName 'Grupp' | ForEach { $_.Group = 'Grupp'; Set-NetFirewallRule -InputObject $_}
```