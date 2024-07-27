# DLink DCS-5010L
Resources for the DLink DCS-5010L

## Firmware

Newer DLink firmware is encrypted but this device just requires a binwalk to extract.

## Getting a shell

Connect UART wires and use `57600` for the baud rate.

```
screen /dev/ttyUSB0 57600
```

## netstat

```
# netstat -tulpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      854/alphapd
tcp        0      0 192.168.0.20:8502       0.0.0.0:*               LISTEN      911/udev
tcp        0      0 0.phapd
udp                             882/lanconfig
udp        0      0 0.0.0.0:2051            0.0.0.0:*                           911/udev
udp        0      0 0.0.0.0:2052            0.0.0.0:*                           2192/mDNSResponder
udp        0      0 0.0.0.0:2053            0.0.0.0:*                           2196/mDN*                           889/mydlinkevent
udp        0                    1593/udhcpd
udp        0      0 0.0.0.0:69              0.0.0.0:*                           883/tftpupload
udp        0      0 0.0.0.0:5978            0.0.0.0:*                           1439/dcp
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           2196/mDNSResponder
udp             2192/mDNSResponder
udp        0      0 0.0.0.0:1900   /udev
```

## ps aux
```
# ps aux
  PID USER       VSZ STAT COMMAND
    1 admin     2176 S    init
    2 admin        0 SWN  [ksoftirqd/0]
    3 admin        0 SW<  [events/0]
    4 admin        0 SW<  [khelper]
    5 admin        0 SW<  [kthread]
   29 admin        0 SW<  [kblockd  [kswapd0]
   47 admin        0 SW   [pdflush]
   48 admin         0 SW<  [cifsdnotifyd]
  609 admin        0 SW   [mtdblockd]
  731 admin     1392 S    nvram_daemon
  854 admin     2752 S    alphapd
  873 admin     1480 S    schedule
  882 admin     1528 S    lanconfig
  883 admin     1408 S    tftpupload1 admin     1980 S    udev
  915 admin     1980 S    udev
  980 S    udev
  961 admin     2172 S    udhcpc -i br0 -s /sbin/udhcpc.sh -p /var/run/udhcpc.p
 1148 admin     2400 S    pcmcmd -s -q 11025 -x 15
 1195 admin     4568 S    uvc_stream -b -m 0 -g 5 -e 5
 1197 admin     4480 S    h264
 1200 admin     in     1168 S    lld2d br0
 1241 admin     2184 S    -sh
 13dmin     1488 S    /mydlink/dcp -i br0 -m DCS-5010L
 1457 admin     4816 S    /mydlink/signalc
 1476 admin     4816 S    /mydlink/signalc
 1477 admin     4816 S    /mydlink/signalc
 15     2172 S    zcip -vf br0 zcip.sh
 2192 admin     1796 S    HNAP S
 3111 admin     2172 S    sleep 5
 3112 admin     2176 R    ps aux
```
