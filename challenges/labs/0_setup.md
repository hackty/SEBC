## List the cloud provider you are using (AWS, GCE, Azure, other)
AWS

## List your instances by their IP address and DNS name
52.73.71.125 ec2-52-73-71-125.compute-1.amazonaws.com ip-172-31-29-207.ec2.internal  
34.224.8.175 ec2-34-224-8-175.compute-1.amazonaws.com ip-172-31-17-205.ec2.internal  
34.201.145.44 ec2-34-201-145-44.compute-1.amazonaws.com ip-172-31-19-87.ec2.internal  
34.202.236.123 ec2-34-202-236-123.compute-1.amazonaws.com ip-172-31-24-15.ec2.internal  
34.224.167.51 ec2-34-224-167-51.compute-1.amazonaws.com ip-172-31-17-48.ec2.internal  

## List the Linux release you are using
CentOS-6.5-GA-03.3-f4325b48-37b0-405a-9847-236c64622e3e-ami-6be4dc02.2 (ami-8997afe0)

## List the file system capacity for the first node
```
[root@ip-172-31-29-207 ~]# df -h /
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        30G  658M   28G   3% /
```

## List the command and output for yum repolist enabled
```
[root@ip-172-31-29-207 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
base                                                                                                                                                | 3.7 kB     00:00     
base/primary_db                                                                                                                                     | 4.7 MB     00:00     
extras                                                                                                                                              | 3.4 kB     00:00     
extras/primary_db                                                                                                                                   |  37 kB     00:00     
updates                                                                                                                                             | 3.4 kB     00:00     
updates/primary_db                                                                                                                                  | 821 kB     00:00     
repo id                                                                      repo name                                                                               status
base                                                                         CentOS-6 - Base                                                                         6,706
extras                                                                       CentOS-6 - Extras                                                                          64
updates                                                                      CentOS-6 - Updates                                                                        270
repolist: 7,040
```
