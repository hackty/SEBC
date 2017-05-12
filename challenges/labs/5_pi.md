```
[chen@ip-172-31-17-205 root]$ kinit chen
Password for chen@HACKTY.CN: 
[chen@ip-172-31-17-205 root]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 100 100
Number of Maps  = 100
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Wrote input for Map #16
Wrote input for Map #17
Wrote input for Map #18
Wrote input for Map #19
Wrote input for Map #20
Wrote input for Map #21
Wrote input for Map #22
Wrote input for Map #23
Wrote input for Map #24
Wrote input for Map #25
Wrote input for Map #26
Wrote input for Map #27
Wrote input for Map #28
Wrote input for Map #29
Wrote input for Map #30
Wrote input for Map #31
Wrote input for Map #32
Wrote input for Map #33
Wrote input for Map #34
Wrote input for Map #35
Wrote input for Map #36
Wrote input for Map #37
Wrote input for Map #38
Wrote input for Map #39
Wrote input for Map #40
Wrote input for Map #41
Wrote input for Map #42
Wrote input for Map #43
Wrote input for Map #44
Wrote input for Map #45
Wrote input for Map #46
Wrote input for Map #47
Wrote input for Map #48
Wrote input for Map #49
Wrote input for Map #50
Wrote input for Map #51
Wrote input for Map #52
Wrote input for Map #53
Wrote input for Map #54
Wrote input for Map #55
Wrote input for Map #56
Wrote input for Map #57
Wrote input for Map #58
Wrote input for Map #59
Wrote input for Map #60
Wrote input for Map #61
Wrote input for Map #62
Wrote input for Map #63
Wrote input for Map #64
Wrote input for Map #65
Wrote input for Map #66
Wrote input for Map #67
Wrote input for Map #68
Wrote input for Map #69
Wrote input for Map #70
Wrote input for Map #71
Wrote input for Map #72
Wrote input for Map #73
Wrote input for Map #74
Wrote input for Map #75
Wrote input for Map #76
Wrote input for Map #77
Wrote input for Map #78
Wrote input for Map #79
Wrote input for Map #80
Wrote input for Map #81
Wrote input for Map #82
Wrote input for Map #83
Wrote input for Map #84
Wrote input for Map #85
Wrote input for Map #86
Wrote input for Map #87
Wrote input for Map #88
Wrote input for Map #89
Wrote input for Map #90
Wrote input for Map #91
Wrote input for Map #92
Wrote input for Map #93
Wrote input for Map #94
Wrote input for Map #95
Wrote input for Map #96
Wrote input for Map #97
Wrote input for Map #98
Wrote input for Map #99
Starting Job
17/05/12 02:58:43 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-205.ec2.internal/172.31.17.205:8032
17/05/12 02:58:43 INFO hdfs.DFSClient: Created token for chen: HDFS_DELEGATION_TOKEN owner=chen@HACKTY.CN, renewer=yarn, realUser=, issueDate=1494557923322, maxDate=149516
2723322, sequenceNumber=3, masterKeyId=2 on 172.31.17.205:802017/05/12 02:58:43 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-205.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.205:8020, Ident: (token f
or chen: HDFS_DELEGATION_TOKEN owner=chen@HACKTY.CN, renewer=yarn, realUser=, issueDate=1494557923322, maxDate=1495162723322, sequenceNumber=3, masterKeyId=2)17/05/12 02:58:43 INFO input.FileInputFormat: Total input paths to process : 100
17/05/12 02:58:43 INFO mapreduce.JobSubmitter: number of splits:100
17/05/12 02:58:43 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494557280734_0003
17/05/12 02:58:43 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.205:8020, Ident: (token for chen: HDFS_DELEGATION_TOKEN owner=chen@HACKTY.CN
, renewer=yarn, realUser=, issueDate=1494557923322, maxDate=1495162723322, sequenceNumber=3, masterKeyId=2)17/05/12 02:58:44 INFO impl.YarnClientImpl: Submitted application application_1494557280734_0003
17/05/12 02:58:44 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-205.ec2.internal:8088/proxy/application_1494557280734_0003/
17/05/12 02:58:44 INFO mapreduce.Job: Running job: job_1494557280734_0003
17/05/12 02:58:53 INFO mapreduce.Job: Job job_1494557280734_0003 running in uber mode : false
17/05/12 02:58:53 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 02:58:59 INFO mapreduce.Job:  map 1% reduce 0%
17/05/12 02:59:04 INFO mapreduce.Job:  map 4% reduce 0%
17/05/12 02:59:07 INFO mapreduce.Job:  map 10% reduce 0%
17/05/12 02:59:09 INFO mapreduce.Job:  map 11% reduce 0%
17/05/12 02:59:10 INFO mapreduce.Job:  map 13% reduce 0%
17/05/12 02:59:14 INFO mapreduce.Job:  map 15% reduce 0%
17/05/12 02:59:15 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 02:59:16 INFO mapreduce.Job:  map 22% reduce 0%
17/05/12 02:59:19 INFO mapreduce.Job:  map 23% reduce 0%
17/05/12 02:59:22 INFO mapreduce.Job:  map 26% reduce 0%
17/05/12 02:59:23 INFO mapreduce.Job:  map 31% reduce 0%
17/05/12 02:59:24 INFO mapreduce.Job:  map 32% reduce 0%
17/05/12 02:59:28 INFO mapreduce.Job:  map 35% reduce 0%
17/05/12 02:59:30 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 02:59:31 INFO mapreduce.Job:  map 41% reduce 0%
17/05/12 02:59:33 INFO mapreduce.Job:  map 42% reduce 0%
17/05/12 02:59:34 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 02:59:38 INFO mapreduce.Job:  map 46% reduce 0%
17/05/12 02:59:39 INFO mapreduce.Job:  map 51% reduce 0%
17/05/12 02:59:40 INFO mapreduce.Job:  map 53% reduce 0%
17/05/12 02:59:45 INFO mapreduce.Job:  map 54% reduce 0%
17/05/12 02:59:46 INFO mapreduce.Job:  map 56% reduce 0%
17/05/12 02:59:47 INFO mapreduce.Job:  map 60% reduce 0%
17/05/12 02:59:48 INFO mapreduce.Job:  map 62% reduce 0%
17/05/12 02:59:49 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 02:59:52 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 02:59:53 INFO mapreduce.Job:  map 65% reduce 0%
17/05/12 02:59:54 INFO mapreduce.Job:  map 66% reduce 0%
17/05/12 02:59:55 INFO mapreduce.Job:  map 70% reduce 0%
17/05/12 02:59:56 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 02:59:59 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 03:00:03 INFO mapreduce.Job:  map 79% reduce 0%
17/05/12 03:00:04 INFO mapreduce.Job:  map 81% reduce 0%
17/05/12 03:00:05 INFO mapreduce.Job:  map 84% reduce 0%
17/05/12 03:00:09 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 03:00:11 INFO mapreduce.Job:  map 88% reduce 0%
17/05/12 03:00:12 INFO mapreduce.Job:  map 92% reduce 0%
17/05/12 03:00:15 INFO mapreduce.Job:  map 93% reduce 0%
17/05/12 03:00:17 INFO mapreduce.Job:  map 95% reduce 31%
17/05/12 03:00:18 INFO mapreduce.Job:  map 97% reduce 31%
17/05/12 03:00:19 INFO mapreduce.Job:  map 100% reduce 31%
17/05/12 03:00:20 INFO mapreduce.Job:  map 100% reduce 100%
17/05/12 03:00:20 INFO mapreduce.Job: Job job_1494557280734_0003 completed successfully
17/05/12 03:00:20 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=461
		FILE: Number of bytes written=12599404
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=28490
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=403
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=100
		Launched reduce tasks=1
		Data-local map tasks=100
		Total time spent by all maps in occupied slots (ms)=626951
		Total time spent by all reduces in occupied slots (ms)=14507
		Total time spent by all map tasks (ms)=626951
		Total time spent by all reduce tasks (ms)=14507
		Total vcore-seconds taken by all map tasks=626951
		Total vcore-seconds taken by all reduce tasks=14507
		Total megabyte-seconds taken by all map tasks=641997824
		Total megabyte-seconds taken by all reduce tasks=14855168
	Map-Reduce Framework
		Map input records=100
		Map output records=200
		Map output bytes=1800
		Map output materialized bytes=3400
		Input split bytes=16690
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=3400
		Reduce input records=200
		Reduce output records=0
		Spilled Records=400
		Shuffled Maps =100
		Failed Shuffles=0
		Merged Map outputs=100
		GC time elapsed (ms)=3846
		CPU time spent (ms)=77480
		Physical memory (bytes) snapshot=45333127168
		Virtual memory (bytes) snapshot=158241685504
		Total committed heap usage (bytes)=52839841792
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=11800
	File Output Format Counters 
		Bytes Written=97
Job Finished in 97.272 seconds
Estimated value of Pi is 3.14080000000000000000
```
