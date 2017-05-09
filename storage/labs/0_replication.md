1.  Choose a partner in class
```
(jnmaomao)
```
2.  Name a source directory after your GitHub handle
```
[root@ip-172-31-27-83 ~]# hadoop fs -mkdir /user/hackty
mkdir: Permission denied: user=root, access=WRITE, inode="/user":hdfs:supergroup:drwxr-xr-x
```
3.  Name a target directory after your partner's GitHub handle
```
[root@ip-172-31-27-83 ~]# hadoop fs -mkdir /user/jnmaomao
mkdir: Permission denied: user=root, access=WRITE, inode="/user":hdfs:supergroup:drwxr-xr-x
```
4.  Use teragen to create a 500 MB file
```
500*1024*1024/100 = 5242880
```
```
[hdfs@ip-172-31-27-83 root]$ hadoop jar /opt/cloudera/parcels/CDH-5.9.2-1.cdh5.9.2.p0.3/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 5242880 /user/hackty/5
m-input17/05/09 03:59:40 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-141.ec2.internal/172.31.17.141:8032
17/05/09 03:59:40 INFO terasort.TeraSort: Generating 5242880 using 2
17/05/09 03:59:40 INFO mapreduce.JobSubmitter: number of splits:2
17/05/09 03:59:41 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494301176616_0002
17/05/09 03:59:41 INFO impl.YarnClientImpl: Submitted application application_1494301176616_0002
17/05/09 03:59:41 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-141.ec2.internal:8088/proxy/application_1494301176616_0002/
17/05/09 03:59:41 INFO mapreduce.Job: Running job: job_1494301176616_0002
17/05/09 03:59:47 INFO mapreduce.Job: Job job_1494301176616_0002 running in uber mode : false
17/05/09 03:59:47 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 04:00:01 INFO mapreduce.Job:  map 95% reduce 0%
17/05/09 04:00:02 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 04:00:02 INFO mapreduce.Job: Job job_1494301176616_0002 completed successfully
17/05/09 04:00:02 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=246576
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=167
		HDFS: Number of bytes written=524288000
		HDFS: Number of read operations=8
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=4
	Job Counters 
		Launched map tasks=2
		Other local map tasks=2
		Total time spent by all maps in occupied slots (ms)=24197
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=24197
		Total vcore-seconds taken by all map tasks=24197
		Total megabyte-seconds taken by all map tasks=24777728
	Map-Reduce Framework
		Map input records=5242880
		Map output records=5242880
		Input split bytes=167
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=233
		CPU time spent (ms)=15420
		Physical memory (bytes) snapshot=741990400
		Virtual memory (bytes) snapshot=3139268608
		Total committed heap usage (bytes)=878706688
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=11257830824958050
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=524288000
```

5.  Copy your partner's file to your target directory
```
[hdfs@ip-172-31-27-83 root]$ hadoop distcp hdfs://ec2-54-201-183-41.us-west-2.compute.amazonaws.com:8020/user/jnmaomao/source/test_data_for_replicate hdfs://ec2-34-207-109
-113.compute-1.amazonaws.com:8020/user/jnmaomao/dest/test_data_for_replicate17/05/09 06:14:04 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=
false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://ec2-54-201-183-41.us-west-2.compute.amazonaws.com:8020/user/jnmaomao/source/test_data_for_replicate], targetPath=hdfs://ec2-34-207-109-113.compute-1.amazonaws.com:8020/user/jnmaomao/dest/test_data_for_replicate, targetPathExists=false, filtersFile='null'}17/05/09 06:14:04 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-141.ec2.internal/172.31.17.141:8032
17/05/09 06:14:04 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/05/09 06:14:04 INFO tools.SimpleCopyListing: Build file listing completed.
17/05/09 06:14:04 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/05/09 06:14:04 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/05/09 06:14:04 INFO tools.DistCp: Number of paths in the copy list: 4
17/05/09 06:14:05 INFO tools.DistCp: Number of paths in the copy list: 4
17/05/09 06:14:05 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-141.ec2.internal/172.31.17.141:8032
17/05/09 06:14:05 INFO mapreduce.JobSubmitter: number of splits:3
17/05/09 06:14:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308265820_0004
17/05/09 06:14:05 INFO impl.YarnClientImpl: Submitted application application_1494308265820_0004
17/05/09 06:14:05 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-141.ec2.internal:8088/proxy/application_1494308265820_0004/
17/05/09 06:14:05 INFO tools.DistCp: DistCp job-id: job_1494308265820_0004
17/05/09 06:14:05 INFO mapreduce.Job: Running job: job_1494308265820_0004
17/05/09 06:14:11 INFO mapreduce.Job: Job job_1494308265820_0004 running in uber mode : false
17/05/09 06:14:11 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 06:14:20 INFO mapreduce.Job:  map 33% reduce 0%
17/05/09 06:14:22 INFO mapreduce.Job:  map 67% reduce 0%
17/05/09 06:14:24 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 06:14:24 INFO mapreduce.Job: Job job_1494308265820_0004 completed successfully
17/05/09 06:14:24 INFO mapreduce.Job: Counters: 33
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=379092
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=524289960
		HDFS: Number of bytes written=524288000
		HDFS: Number of read operations=56
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=13
	Job Counters 
		Launched map tasks=3
		Other local map tasks=3
		Total time spent by all maps in occupied slots (ms)=22700
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=22700
		Total vcore-seconds taken by all map tasks=22700
		Total megabyte-seconds taken by all map tasks=23244800
	Map-Reduce Framework
		Map input records=4
		Map output records=0
		Input split bytes=342
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=221
		CPU time spent (ms)=12440
		Physical memory (bytes) snapshot=689627136
		Virtual memory (bytes) snapshot=4715294720
		Total committed heap usage (bytes)=1080557568
	File Input Format Counters 
		Bytes Read=1618
	File Output Format Counters 
		Bytes Written=0
	org.apache.hadoop.tools.mapred.CopyMapper$Counter
		BYTESCOPIED=524288000
		BYTESEXPECTED=524288000
		COPY=4
```

6.  Browse the results
```
[hdfs@ip-172-31-27-83 root]$ hadoop fs -ls /user/jnmaomao/dest/test_data_for_replicate
Found 3 items
-rw-r--r--   3 hdfs supergroup          0 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/_SUCCESS
-rw-r--r--   3 hdfs supergroup  262144000 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/part-m-00000
-rw-r--r--   3 hdfs supergroup  262144000 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/part-m-00001
```

```
[hdfs@ip-172-31-27-83 root]$ hadoop fs -ls /user/jnmaomao/dest/test_data_for_replicate
Found 3 items
-rw-r--r--   3 hdfs supergroup          0 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/_SUCCESS
-rw-r--r--   3 hdfs supergroup  262144000 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/part-m-00000
-rw-r--r--   3 hdfs supergroup  262144000 2017-05-09 06:14 /user/jnmaomao/dest/test_data_for_replicate/part-m-00001
[hdfs@ip-172-31-27-83 root]$ hdfs fsck /user/jnmaomao/dest/test_data_for_replicate -files -blocks
Connecting to namenode via http://ip-172-31-17-141.ec2.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.27.83 for path /user/jnmaomao/dest/test_data_for_replicate at Tue May 09 06:18:09 UTC 2017
/user/jnmaomao/dest/test_data_for_replicate <dir>
/user/jnmaomao/dest/test_data_for_replicate/_SUCCESS 0 bytes, 0 block(s):  OK

/user/jnmaomao/dest/test_data_for_replicate/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-538619430-172.31.17.141-1494268033933:blk_1073742820_1996 len=134217728 Live_repl=3
1. BP-538619430-172.31.17.141-1494268033933:blk_1073742822_1998 len=127926272 Live_repl=3

/user/jnmaomao/dest/test_data_for_replicate/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-538619430-172.31.17.141-1494268033933:blk_1073742818_1994 len=134217728 Live_repl=3
1. BP-538619430-172.31.17.141-1494268033933:blk_1073742821_1997 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:	524288000 B
 Total dirs:	1
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 131072000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Tue May 09 06:18:09 UTC 2017 in 3 milliseconds


The filesystem under path '/user/jnmaomao/dest/test_data_for_replicate' is HEALTHY
```
