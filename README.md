# HW22_VPN
TAP

Server:
```
[vagrant@server ~]$ sudo -i
[root@server ~]# iperf3 -s &
[1] 26620
[root@server ~]# -----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------
Accepted connection from 10.10.10.2, port 44896
[  5] local 10.10.10.1 port 5201 connected to 10.10.10.2 port 44898
[ ID] Interval           Transfer     Bitrate
[  5]   0.00-1.00   sec  14.7 MBytes   124 Mbits/sec                  
[  5]   1.00-2.00   sec  18.8 MBytes   158 Mbits/sec                  
[  5]   2.00-3.00   sec  19.5 MBytes   163 Mbits/sec                  
[  5]   3.00-4.00   sec  19.5 MBytes   164 Mbits/sec                  
[  5]   4.00-5.00   sec  19.2 MBytes   161 Mbits/sec                  
[  5]   5.00-6.00   sec  19.4 MBytes   163 Mbits/sec                  
[  5]   6.00-7.00   sec  19.5 MBytes   163 Mbits/sec                  
[  5]   7.00-8.00   sec  19.6 MBytes   165 Mbits/sec                  
[  5]   8.00-9.00   sec  19.5 MBytes   164 Mbits/sec                  
[  5]   9.00-10.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  10.00-11.00  sec  19.5 MBytes   163 Mbits/sec                  
[  5]  11.00-12.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  12.00-13.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  13.00-14.00  sec  19.3 MBytes   162 Mbits/sec                  
[  5]  14.00-15.00  sec  19.2 MBytes   161 Mbits/sec                  
[root@server ~]# [  5]  15.00-16.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  16.00-17.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  17.00-18.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  18.00-19.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  19.00-20.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  20.00-21.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  21.00-22.00  sec  19.2 MBytes   161 Mbits/sec                  
[  5]  22.00-23.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  23.00-24.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  24.00-25.00  sec  19.7 MBytes   165 Mbits/sec                  
[  5]  25.00-26.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  26.00-27.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  27.00-28.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  28.00-29.00  sec  19.3 MBytes   162 Mbits/sec                  
[  5]  29.00-30.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  30.00-31.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  31.00-32.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  32.00-33.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  33.00-34.00  sec  19.5 MBytes   163 Mbits/sec                  
[  5]  34.00-35.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  35.00-36.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  36.00-37.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  37.00-38.00  sec  19.5 MBytes   163 Mbits/sec                  
[  5]  38.00-39.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  39.00-40.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  40.00-40.26  sec   912 KBytes  28.6 Mbits/sec                  
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate
[  5]   0.00-40.26  sec   775 MBytes   161 Mbits/sec                  receiver
-----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------
```
Client:
```
[root@client ~]# iperf3 -c 10.10.10.1 -t 40 -i 5
Connecting to host 10.10.10.1, port 5201
[  5] local 10.10.10.2 port 44898 connected to 10.10.10.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-5.01   sec  92.8 MBytes   155 Mbits/sec   33    102 KBytes       
[  5]   5.01-10.01  sec  97.5 MBytes   164 Mbits/sec   35   90.3 KBytes       
[  5]  10.01-15.01  sec  96.7 MBytes   162 Mbits/sec   42    110 KBytes       
[  5]  15.01-20.01  sec  97.8 MBytes   164 Mbits/sec   39   83.9 KBytes       
[  5]  20.01-25.01  sec  97.5 MBytes   164 Mbits/sec   46    101 KBytes       
[  5]  25.01-30.01  sec  97.6 MBytes   164 Mbits/sec   39    114 KBytes       
[  5]  30.01-35.00  sec  97.6 MBytes   164 Mbits/sec   38    101 KBytes       
[  5]  35.00-40.01  sec  97.5 MBytes   163 Mbits/sec   47    114 KBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-40.01  sec   775 MBytes   163 Mbits/sec  319             sender
[  5]   0.00-40.26  sec   775 MBytes   161 Mbits/sec                  receiver

iperf Done.
```

TUN
Server:
```
[vagrant@server ~]$ sudo -i
[root@server ~]# iperf3 -s &
[1] 24223
[root@server ~]# -----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------
Accepted connection from 10.10.10.2, port 39262
[  5] local 10.10.10.1 port 5201 connected to 10.10.10.2 port 39264
[ ID] Interval           Transfer     Bitrate
[  5]   0.00-1.00   sec  15.0 MBytes   126 Mbits/sec                  
[  5]   1.00-2.00   sec  18.6 MBytes   156 Mbits/sec                  
[  5]   2.00-3.00   sec  19.7 MBytes   165 Mbits/sec                  
[  5]   3.00-4.00   sec  19.6 MBytes   164 Mbits/sec                  
[  5]   4.00-5.00   sec  19.7 MBytes   165 Mbits/sec                  
[  5]   5.00-6.00   sec  19.6 MBytes   164 Mbits/sec                  
[  5]   6.00-7.00   sec  19.6 MBytes   164 Mbits/sec                  
[  5]   7.00-8.00   sec  19.5 MBytes   164 Mbits/sec                  
[  5]   8.00-9.00   sec  19.6 MBytes   165 Mbits/sec                  
[  5]   9.00-10.00  sec  19.8 MBytes   166 Mbits/sec                  
[  5]  10.00-11.00  sec  19.8 MBytes   166 Mbits/sec                  
[  5]  11.00-12.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  12.00-13.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  13.00-14.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  14.00-15.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  15.00-16.00  sec  19.0 MBytes   159 Mbits/sec                  
[  5]  16.00-17.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  17.00-18.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  18.00-19.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  19.00-20.00  sec  20.1 MBytes   168 Mbits/sec                  
[  5]  20.00-21.00  sec  19.8 MBytes   166 Mbits/sec                  
[  5]  21.00-22.00  sec  19.8 MBytes   166 Mbits/sec                  
[  5]  22.00-23.00  sec  20.1 MBytes   168 Mbits/sec                  
[  5]  23.00-24.00  sec  19.3 MBytes   162 Mbits/sec                  
[  5]  24.00-25.00  sec  20.0 MBytes   167 Mbits/sec                  
[  5]  25.00-26.00  sec  19.7 MBytes   166 Mbits/sec                  
[  5]  26.00-27.00  sec  20.1 MBytes   169 Mbits/sec                  
[  5]  27.00-28.00  sec  19.6 MBytes   164 Mbits/sec                  
[  5]  28.00-29.00  sec  19.7 MBytes   165 Mbits/sec                  
[  5]  29.00-30.00  sec  19.6 MBytes   165 Mbits/sec                  
[  5]  30.00-31.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  31.00-32.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  32.00-33.00  sec  18.9 MBytes   158 Mbits/sec                  
[  5]  33.00-34.00  sec  19.5 MBytes   164 Mbits/sec                  
[  5]  34.00-35.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  35.00-36.00  sec  19.4 MBytes   163 Mbits/sec                  
[root@server ~]# [  5]  36.00-37.00  sec  19.1 MBytes   160 Mbits/sec                  
[  5]  37.00-38.00  sec  18.9 MBytes   158 Mbits/sec                  
[  5]  38.00-39.00  sec  18.7 MBytes   157 Mbits/sec                  
[  5]  39.00-40.00  sec  19.4 MBytes   163 Mbits/sec                  
[  5]  40.00-40.03  sec   511 KBytes   149 Mbits/sec                  
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate
[  5]   0.00-40.03  sec   777 MBytes   163 Mbits/sec                  receiver
-----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------

```
Client:
```
[vagrant@client ~]$ sudo -i
[root@client ~]# iperf3 -c 10.10.10.1 -t 40 -i 5
Connecting to host 10.10.10.1, port 5201
[  5] local 10.10.10.2 port 39264 connected to 10.10.10.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-5.01   sec  93.7 MBytes   157 Mbits/sec   35   87.2 KBytes       
[  5]   5.01-10.01  sec  98.1 MBytes   165 Mbits/sec   42    106 KBytes       
[  5]  10.01-15.01  sec  97.8 MBytes   164 Mbits/sec   41    116 KBytes       
[  5]  15.01-20.00  sec  97.5 MBytes   164 Mbits/sec   43   81.9 KBytes       
[  5]  20.00-25.01  sec  99.3 MBytes   166 Mbits/sec   49    111 KBytes       
[  5]  25.01-30.01  sec  98.6 MBytes   166 Mbits/sec   40    123 KBytes       
[  5]  30.01-35.01  sec  96.9 MBytes   162 Mbits/sec   40    120 KBytes       
[  5]  35.01-40.00  sec  95.2 MBytes   160 Mbits/sec   43    100 KBytes       
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-40.00  sec   777 MBytes   163 Mbits/sec  333             sender
[  5]   0.00-40.03  sec   777 MBytes   163 Mbits/sec                  receiver

iperf Done.

```
RAS
```
[vagrant@client ~]$ ping -c 4 10.10.10.1
PING 10.10.10.1 (10.10.10.1) 56(84) bytes of data.
64 bytes from 10.10.10.1: icmp_seq=1 ttl=64 time=1.10 ms
64 bytes from 10.10.10.1: icmp_seq=2 ttl=64 time=1.00 ms
64 bytes from 10.10.10.1: icmp_seq=3 ttl=64 time=1.01 ms
64 bytes from 10.10.10.1: icmp_seq=4 ttl=64 time=1.02 ms

--- 10.10.10.1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 1.002/1.032/1.095/0.043 ms
[vagrant@client ~]$ ip r
default via 10.0.2.2 dev eth0 proto dhcp metric 101 
10.0.2.0/24 dev eth0 proto kernel scope link src 10.0.2.15 metric 101 
10.10.10.0/24 via 10.10.10.5 dev tun0 
10.10.10.5 dev tun0 proto kernel scope link src 10.10.10.6 
192.168.56.0/24 dev eth1 proto kernel scope link src 192.168.56.20 metric 100
```
