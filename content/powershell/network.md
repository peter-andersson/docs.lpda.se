---
title: Network
---

#### Test network connection
```ps1
Test-NetConnection thomasmaurer.ch -CommonTCPPort RDP
Test-NetConnection thomasmaurer.ch -TraceRoute

Test-NetConnection 127.0.0.1 -Port 4044
```

#### Portforward
```ps1
netsh interface portproxy delete v4tov4 listenport=4088 listenaddress=127.0.0.1

netsh interface portproxy add v4tov4 listenport=4088 listenaddress=127.0.0.1 connectaddress=127.0.0.1 connectport=4044
```