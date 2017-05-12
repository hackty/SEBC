```
[zhou@ip-172-31-17-205 root]$ kinit zhou
Password for zhou@HACKTY.CN: 
[zhou@ip-172-31-17-205 root]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/zhou/tgen /user/zhou/tsort
17/05/12 02:51:58 INFO terasort.TeraSort: starting
17/05/12 02:52:00 INFO hdfs.DFSClient: Created token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@HACKTY.CN, renewer=yarn, realUser=, issueDate=1494557520214, maxDate=149516
2320214, sequenceNumber=1, masterKeyId=2 on 172.31.17.205:802017/05/12 02:52:00 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-205.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.205:8020, Ident: (token f
or zhou: HDFS_DELEGATION_TOKEN owner=zhou@HACKTY.CN, renewer=yarn, realUser=, issueDate=1494557520214, maxDate=1495162320214, sequenceNumber=1, masterKeyId=2)17/05/12 02:52:00 INFO input.FileInputFormat: Total input paths to process : 6
Spent 383ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 388ms
Sampling 10 splits of 102
Making 8 from 100000 sampled records
Computing parititions took 993ms
Spent 1383ms computing partitions.
17/05/12 02:52:01 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-205.ec2.internal/172.31.17.205:8032
17/05/12 02:52:01 INFO mapreduce.JobSubmitter: number of splits:102
17/05/12 02:52:02 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494557280734_0001
17/05/12 02:52:02 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.205:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@HACKTY.CN
, renewer=yarn, realUser=, issueDate=1494557520214, maxDate=1495162320214, sequenceNumber=1, masterKeyId=2)17/05/12 02:52:03 INFO impl.YarnClientImpl: Submitted application application_1494557280734_0001
17/05/12 02:52:03 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-205.ec2.internal:8088/proxy/application_1494557280734_0001/
17/05/12 02:52:03 INFO mapreduce.Job: Running job: job_1494557280734_0001
17/05/12 02:52:14 INFO mapreduce.Job: Job job_1494557280734_0001 running in uber mode : false
17/05/12 02:52:14 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 02:52:24 INFO mapreduce.Job:  map 2% reduce 0%
17/05/12 02:52:29 INFO mapreduce.Job:  map 4% reduce 0%
17/05/12 02:52:30 INFO mapreduce.Job:  map 6% reduce 0%
17/05/12 02:52:33 INFO mapreduce.Job:  map 9% reduce 0%
17/05/12 02:52:34 INFO mapreduce.Job:  map 11% reduce 0%
17/05/12 02:52:39 INFO mapreduce.Job:  map 15% reduce 0%
17/05/12 02:52:44 INFO mapreduce.Job:  map 17% reduce 0%
17/05/12 02:52:47 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 02:52:48 INFO mapreduce.Job:  map 22% reduce 0%
17/05/12 02:52:50 INFO mapreduce.Job:  map 24% reduce 0%
17/05/12 02:52:54 INFO mapreduce.Job:  map 25% reduce 0%
17/05/12 02:52:58 INFO mapreduce.Job:  map 28% reduce 0%
17/05/12 02:52:59 INFO mapreduce.Job:  map 30% reduce 0%
17/05/12 02:53:00 INFO mapreduce.Job:  map 32% reduce 0%
17/05/12 02:53:03 INFO mapreduce.Job:  map 34% reduce 0%
17/05/12 02:53:06 INFO mapreduce.Job:  map 35% reduce 0%
17/05/12 02:53:07 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 02:53:08 INFO mapreduce.Job:  map 38% reduce 0%
17/05/12 02:53:10 INFO mapreduce.Job:  map 39% reduce 0%
17/05/12 02:53:11 INFO mapreduce.Job:  map 41% reduce 0%
17/05/12 02:53:13 INFO mapreduce.Job:  map 43% reduce 0%
17/05/12 02:53:15 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 02:53:16 INFO mapreduce.Job:  map 45% reduce 0%
17/05/12 02:53:17 INFO mapreduce.Job:  map 46% reduce 0%
17/05/12 02:53:18 INFO mapreduce.Job:  map 47% reduce 0%
17/05/12 02:53:21 INFO mapreduce.Job:  map 48% reduce 0%
17/05/12 02:53:22 INFO mapreduce.Job:  map 50% reduce 0%
17/05/12 02:53:23 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 02:53:24 INFO mapreduce.Job:  map 53% reduce 0%
17/05/12 02:53:25 INFO mapreduce.Job:  map 54% reduce 0%
17/05/12 02:53:26 INFO mapreduce.Job:  map 55% reduce 0%
17/05/12 02:53:27 INFO mapreduce.Job:  map 56% reduce 0%
17/05/12 02:53:32 INFO mapreduce.Job:  map 58% reduce 0%
17/05/12 02:53:33 INFO mapreduce.Job:  map 60% reduce 0%
17/05/12 02:53:34 INFO mapreduce.Job:  map 61% reduce 0%
17/05/12 02:53:35 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 02:53:36 INFO mapreduce.Job:  map 65% reduce 0%
17/05/12 02:53:40 INFO mapreduce.Job:  map 67% reduce 0%
17/05/12 02:53:42 INFO mapreduce.Job:  map 68% reduce 0%
17/05/12 02:53:43 INFO mapreduce.Job:  map 70% reduce 0%
17/05/12 02:53:44 INFO mapreduce.Job:  map 71% reduce 0%
17/05/12 02:53:45 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 02:53:47 INFO mapreduce.Job:  map 74% reduce 0%
17/05/12 02:53:49 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 02:53:51 INFO mapreduce.Job:  map 76% reduce 0%
17/05/12 02:53:52 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 02:53:53 INFO mapreduce.Job:  map 78% reduce 0%
17/05/12 02:53:54 INFO mapreduce.Job:  map 80% reduce 0%
17/05/12 02:53:59 INFO mapreduce.Job:  map 84% reduce 0%
17/05/12 02:54:00 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 02:54:01 INFO mapreduce.Job:  map 86% reduce 0%
17/05/12 02:54:02 INFO mapreduce.Job:  map 87% reduce 0%
17/05/12 02:54:03 INFO mapreduce.Job:  map 88% reduce 0%
17/05/12 02:54:05 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 02:54:08 INFO mapreduce.Job:  map 90% reduce 0%
17/05/12 02:54:10 INFO mapreduce.Job:  map 92% reduce 3%
17/05/12 02:54:11 INFO mapreduce.Job:  map 93% reduce 3%
17/05/12 02:54:12 INFO mapreduce.Job:  map 93% reduce 6%
17/05/12 02:54:13 INFO mapreduce.Job:  map 93% reduce 10%
17/05/12 02:54:15 INFO mapreduce.Job:  map 93% reduce 15%
17/05/12 02:54:16 INFO mapreduce.Job:  map 95% reduce 15%
17/05/12 02:54:18 INFO mapreduce.Job:  map 96% reduce 18%
17/05/12 02:54:20 INFO mapreduce.Job:  map 97% reduce 18%
17/05/12 02:54:21 INFO mapreduce.Job:  map 97% reduce 20%
17/05/12 02:54:22 INFO mapreduce.Job:  map 99% reduce 20%
17/05/12 02:54:24 INFO mapreduce.Job:  map 100% reduce 20%
17/05/12 02:54:25 INFO mapreduce.Job:  map 100% reduce 21%
17/05/12 02:54:27 INFO mapreduce.Job:  map 100% reduce 29%
17/05/12 02:54:28 INFO mapreduce.Job:  map 100% reduce 42%
17/05/12 02:54:30 INFO mapreduce.Job:  map 100% reduce 43%
17/05/12 02:54:31 INFO mapreduce.Job:  map 100% reduce 48%
17/05/12 02:54:33 INFO mapreduce.Job:  map 100% reduce 56%
17/05/12 02:54:34 INFO mapreduce.Job:  map 100% reduce 60%
17/05/12 02:54:36 INFO mapreduce.Job:  map 100% reduce 64%
17/05/12 02:54:37 INFO mapreduce.Job:  map 100% reduce 68%
17/05/12 02:54:39 INFO mapreduce.Job:  map 100% reduce 77%
17/05/12 02:54:40 INFO mapreduce.Job:  map 100% reduce 83%
17/05/12 02:54:42 INFO mapreduce.Job:  map 100% reduce 85%
17/05/12 02:54:43 INFO mapreduce.Job:  map 100% reduce 87%
17/05/12 02:54:45 INFO mapreduce.Job:  map 100% reduce 89%
17/05/12 02:54:46 INFO mapreduce.Job:  map 100% reduce 92%
17/05/12 02:54:48 INFO mapreduce.Job:  map 100% reduce 94%
17/05/12 02:54:49 INFO mapreduce.Job:  map 100% reduce 96%
17/05/12 02:54:50 INFO mapreduce.Job:  map 100% reduce 97%
17/05/12 02:54:51 INFO mapreduce.Job:  map 100% reduce 98%
17/05/12 02:54:52 INFO mapreduce.Job:  map 100% reduce 99%
17/05/12 02:54:54 INFO mapreduce.Job:  map 100% reduce 100%
17/05/12 02:54:54 INFO mapreduce.Job: Job job_1494557280734_0001 completed successfully
17/05/12 02:54:54 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2932347287
		FILE: Number of bytes written=5819213722
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=6553613668
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=330
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=102
		Launched reduce tasks=8
		Data-local map tasks=101
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=929875
		Total time spent by all reduces in occupied slots (ms)=290427
		Total time spent by all map tasks (ms)=929875
		Total time spent by all reduce tasks (ms)=290427
		Total vcore-seconds taken by all map tasks=929875
		Total vcore-seconds taken by all reduce tasks=290427
		Total megabyte-seconds taken by all map tasks=952192000
		Total megabyte-seconds taken by all reduce tasks=297397248
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Map output bytes=6684672000
		Map output materialized bytes=2873061739
		Input split bytes=13668
		Combine input records=0
		Combine output records=0
		Reduce input groups=65536000
		Reduce shuffle bytes=2873061739
		Reduce input records=65536000
		Reduce output records=65536000
		Spilled Records=131072000
		Shuffled Maps =816
		Failed Shuffles=0
		Merged Map outputs=816
		GC time elapsed (ms)=17470
		CPU time spent (ms)=744230
		Physical memory (bytes) snapshot=57831821312
		Virtual memory (bytes) snapshot=172187017216
		Total committed heap usage (bytes)=65931313152
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=6553600000
	File Output Format Counters 
		Bytes Written=6553600000
17/05/12 02:54:54 INFO terasort.TeraSort: done
[zhou@ip-172-31-17-205 root]$ hadoop fs -ls /user/zhou/tsort
Found 10 items
-rw-r--r--   1 zhou zhou          0 2017-05-12 02:54 /user/zhou/tsort/_SUCCESS
-rw-r--r--  10 zhou zhou         77 2017-05-12 02:52 /user/zhou/tsort/_partition.lst
-rw-r--r--   1 zhou zhou  815319700 2017-05-12 02:54 /user/zhou/tsort/part-r-00000
-rw-r--r--   1 zhou zhou  811351600 2017-05-12 02:54 /user/zhou/tsort/part-r-00001
-rw-r--r--   1 zhou zhou  838071400 2017-05-12 02:54 /user/zhou/tsort/part-r-00002
-rw-r--r--   1 zhou zhou  822251600 2017-05-12 02:54 /user/zhou/tsort/part-r-00003
-rw-r--r--   1 zhou zhou  816776200 2017-05-12 02:54 /user/zhou/tsort/part-r-00004
-rw-r--r--   1 zhou zhou  817977900 2017-05-12 02:54 /user/zhou/tsort/part-r-00005
-rw-r--r--   1 zhou zhou  820234400 2017-05-12 02:54 /user/zhou/tsort/part-r-00006
-rw-r--r--   1 zhou zhou  811617200 2017-05-12 02:54 /user/zhou/tsort/part-r-00007
```
