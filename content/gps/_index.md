---
title: GPS
chapter: true
---

# GPS

## NMEA
http://www.gpsinformation.org/dale/nmea.htm#nmea

## Novatel
### Base Station
```
FIX POSITION lat long hgt (hgt is geoid/MSL height) 
LOG COM2 RTCM1 ONTIME 5 
LOG COM2 RTCM3 ONTIME 10 
LOG COM2 RTCM22 ONTIME 10,1 
LOG COM2 RTCM1819 ONTIME 1 
COM COM2 9600 N 8 1 N OFF 
INTERFACEMODE COM2 NONE RTCM OFF 
SAVECONFIG (optional) 
```

### Remote Rover
```
COM COM2 9600 N 8 1 N OFF 
INTERFACEMODE COM2 RTCM NONE OFF 
SAVECONFIG (optional) 
```