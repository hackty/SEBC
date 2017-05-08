
1.  Check vm.swappiness on all your nodes  
Set the value to 1 if necessary  
```
[root@ip-172-31-26-151 ~]# cat /proc/sys/vm/swappiness
30
[root@ip-172-31-26-151 ~]# echo 1 > /proc/sys/vm/swappiness
[root@ip-172-31-26-151 ~]# cat /proc/sys/vm/swappiness
1
```  

2.  Show the mount attributes of your volume(s)
```
[root@ip-172-31-26-151 ~]# mount -l
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599292k,nr_inodes=1899823,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=27,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497296k,mode=700)
```
```
[root@ip-172-31-26-151 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.2G   29G   4% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
```

3.  If you have ext-based volumes, list the reserve space setting  
XFS volumes do not support reserve space  
```
[root@ip-172-31-26-151 ~]# mount |grep xvda
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
```
XFS volumes do not support reserve space   

4.  Disable transparent hugepage support  
```
[root@ip-172-31-26-151 ~]# cat /proc/sys/vm/nr_hugepages
0
```

5.  List your network interface configuration  
```
[root@ip-172-31-26-151 ~]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.26.151  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::870:6fff:fe4b:adba  prefixlen 64  scopeid 0x20<link>
        ether 0a:70:6f:4b:ad:ba  txqueuelen 1000  (Ethernet)
        RX packets 1714  bytes 176220 (172.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1690  bytes 354810 (346.4 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 4  bytes 340 (340.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4  bytes 340 (340.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

6.  Show that forward and reverse host lookups are correctly resolved
```
[root@ip-172-31-26-151 ~]# getent hosts
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
```

```
[root@ip-172-31-26-151 ~]# nslookup `hostname`
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-26-151.ec2.internal
Address: 172.31.26.151
```

7.  Show the nscd service is running  
```
[root@ip-172-31-26-151 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-05-08 04:40:09 EDT; 8s ago
  Process: 9983 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9984 (nscd)
   CGroup: /system.slice/nscd.service
           └─9984 /usr/sbin/nscd

May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring file `/etc/hosts` (4)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring directory `/etc` (2)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring file `/etc/resolv.conf` (5)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring directory `/etc` (2)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring file `/etc/services` (6)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 monitoring directory `/etc` (2)
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
May 08 04:40:09 ip-172-31-26-151.ec2.internal nscd[9984]: 9984 Access Vector Cache (AVC) started
May 08 04:40:09 ip-172-31-26-151.ec2.internal systemd[1]: Started Name Service Cache Daemon.
```

8.  Show the ntpd service is running
```
[root@ip-172-31-26-151 ~]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-05-08 04:42:00 EDT; 27s ago
  Process: 10095 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 10096 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─10096 /usr/sbin/ntpd -u ntp:ntp -g

May 08 04:41:59 ip-172-31-26-151.ec2.internal ntpd[10096]: Listen normally on 2 lo 127.0.0.1 UDP 123
May 08 04:41:59 ip-172-31-26-151.ec2.internal ntpd[10096]: Listen normally on 3 eth0 172.31.26.151 UDP 123
May 08 04:41:59 ip-172-31-26-151.ec2.internal ntpd[10096]: Listen normally on 4 lo ::1 UDP 123
May 08 04:41:59 ip-172-31-26-151.ec2.internal ntpd[10096]: Listen normally on 5 eth0 fe80::870:6fff:fe4b:adba UDP 123
May 08 04:41:59 ip-172-31-26-151.ec2.internal ntpd[10096]: Listening on routing socket on fd #22 for interface updates
May 08 04:42:00 ip-172-31-26-151.ec2.internal systemd[1]: Started Network Time Service.
May 08 04:42:00 ip-172-31-26-151.ec2.internal ntpd[10096]: 0.0.0.0 c016 06 restart
May 08 04:42:00 ip-172-31-26-151.ec2.internal ntpd[10096]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
May 08 04:42:00 ip-172-31-26-151.ec2.internal ntpd[10096]: 0.0.0.0 c011 01 freq_not_set
May 08 04:42:07 ip-172-31-26-151.ec2.internal ntpd[10096]: 0.0.0.0 c614 04 freq_mode
```

