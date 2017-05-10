
1.  Check vm.swappiness on all your nodes  
Set the value to 1 if necessary  
```
[root@ip-172-31-27-83 ~]# cat /proc/sys/vm/swappiness
60
[root@ip-172-31-27-83 ~]# echo 1 > /proc/sys/vm/swappiness
[root@ip-172-31-27-83 ~]# echo 'vm.swappiness=1'>> /etc/sysctl.conf
[root@ip-172-31-27-83 ~]# cat /proc/sys/vm/swappiness
1
```  

2.  Show the mount attributes of your volume(s)
```
[root@ip-172-31-27-83 ~]# mount -ls
/dev/xvde on / type ext4 (rw) [centos_root]
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
```

3.  If you have ext-based volumes, list the reserve space setting  
XFS volumes do not support reserve space  
```
[root@ip-172-31-27-83 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing required
old desc_blocks = 1, new_desc_blocks = 2
Performing an on-line resize of /dev/xvde to 7864320 (4k) blocks.
The filesystem on /dev/xvde is now 7864320 blocks long.

[root@ip-172-31-27-83 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        30G  654M   28G   3% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

4.  Disable transparent hugepage support  
```
[root@ip-172-31-27-83 ~]# cat /proc/sys/vm/nr_hugepages
0
```

5.  List your network interface configuration  
```
[root@ip-172-31-27-83 ~]# ifconfig
eth0      Link encap:Ethernet  HWaddr 0A:3D:3C:32:B9:20  
          inet addr:172.31.27.83  Bcast:172.31.31.255  Mask:255.255.240.0
          inet6 addr: fe80::83d:3cff:fe32:b920/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:62 errors:0 dropped:0 overruns:0 frame:0
          TX packets:68 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:6943 (6.7 KiB)  TX bytes:9112 (8.8 KiB)
          Interrupt:24 

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)
```

6.  Show that forward and reverse host lookups are correctly resolved
```
[root@ip-172-31-27-83 ~]# getent hosts
127.0.0.1       localhost.localdomain localhost
127.0.0.1       localhost6.localdomain6 localhost6
```
(no need to alter hosts owing to dns provided by aws)
```
[root@ip-172-31-27-83 ~]# nslookup `hostname`
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-27-83.ec2.internal
Address: 172.31.27.83

[root@ip-172-31-27-83 ~]# ping ip-172-31-31-221.ec2.internal
PING ip-172-31-31-221.ec2.internal (172.31.31.221) 56(84) bytes of data.
64 bytes from ip-172-31-31-221.ec2.internal (172.31.31.221): icmp_seq=1 ttl=64 time=2.08 ms
64 bytes from ip-172-31-31-221.ec2.internal (172.31.31.221): icmp_seq=2 ttl=64 time=0.279 ms
64 bytes from ip-172-31-31-221.ec2.internal (172.31.31.221): icmp_seq=3 ttl=64 time=0.424 ms
^C
--- ip-172-31-31-221.ec2.internal ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2293ms
rtt min/avg/max/mdev = 0.279/0.930/2.089/0.821 ms

```

7.  Show the nscd service is running  
```
[root@ip-172-31-27-83 ~]# service nscd status
nscd (pid 1028) is running...
```

8.  Show the ntpd service is running
```
[root@ip-172-31-27-83 ~]# service ntpd status
ntpd (pid  1092) is running...
```

