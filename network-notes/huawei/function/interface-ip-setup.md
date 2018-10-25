# 接口IP配置及描述
为R1的S1/0/0接口配置IP地址，配置IP地址时可以使用子婴掩码长度，也可以使用完整的子网掩码，如掩码为255.255.255.0，也可以使用24替代

```
[R1]interface Serial 1/0/0
[R1-Serial1/0/0]ip address 10.0.12.1 24
[R1-Serial1/0/0]description This interface connect to R2-S1/0/0
```

用display this命令检查配置结果

```
[R1-Serial1/0/0]display this
[V200R003C00]
#
interface Serial1/0/0
 link-protocol ppp
 description This interface connect to R2-S1/0/0
 ip address 10.0.12.1 255.255.255.0 
#
return
```

用display interface命令查看接口详细信息
```
[R1-Serial1/0/0]display interface Serial1/0/0
Serial1/0/0 current state : UP
Line protocol current state : UP
Description:This interface connect to R2-S1/0/0
Route Port,The Maximum Transmit Unit is 1500, Hold timer is 10(sec)
Internet Address is 10.0.12.1/24
Link layer protocol is PPP
LCP initial
Last physical up time   : -
Last physical down time : 2018-10-25 13:47:08 UTC-08:00
Current system time: 2018-10-25 13:53:52-08:00
Physical layer is synchronous, Virtualbaudrate is 64000 bps
Interface is DTE, Cable type is V11, Clock mode is TC
Last 300 seconds input rate 0 bytes/sec 0 bits/sec 0 packets/sec
Last 300 seconds output rate 0 bytes/sec 0 bits/sec 0 packets/sec

Input: 0 packets, 0 bytes
  Broadcast:              0,  Multicast:              0
  Errors:                 0,  Runts:                  0
  Giants:                 0,  CRC:                    0

  Alignments:             0,  Overruns:               0
  Dribbles:               0,  Aborts:                 0
  No Buffers:             0,  Frame Error:            0

Output: 0 packets, 0 bytes
  Total Error:            0,  Overruns:               0
  Collisions:             0,  Deferred:               0
    Input bandwidth utilization  :    0%
    Output bandwidth utilization :    0%

[R1-Serial1/0/0]
```