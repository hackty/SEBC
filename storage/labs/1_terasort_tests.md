1.  Create an end-user Linux account named with your GitHub handle  
```
[root@ip-172-31-27-83 ~]# useradd hackty
```
Create an HDFS directory under /user
```
[root@ip-172-31-27-83 ~]# hadoop fs -mkdir /user/hackty
mkdir: `/user/hackty': File exists
```


2.  Create a 10 GB file using teragen  
Set the number of mappers to four  
Limit the block size to 32 MB  
Land the output in your user's home directory  
Use the time command to report the job's duration
```
[hackty@ip-172-31-27-83 root]$ time hadoop jar /opt/cloudera/parcels/CDH-5.9.2-1.cdh5.9.2.p0.3/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapred.map.task
s=4 -Ddfs.block.size=33554432 107374182 /user/hackty/10g-input17/05/09 07:19:23 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-141.ec2.internal/172.31.17.141:8032
17/05/09 07:19:24 INFO terasort.TeraSort: Generating 107374182 using 4
17/05/09 07:19:24 INFO mapreduce.JobSubmitter: number of splits:4
17/05/09 07:19:24 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/09 07:19:24 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/05/09 07:19:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308265820_0005
17/05/09 07:19:25 INFO impl.YarnClientImpl: Submitted application application_1494308265820_0005
17/05/09 07:19:25 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-141.ec2.internal:8088/proxy/application_1494308265820_0005/
17/05/09 07:19:25 INFO mapreduce.Job: Running job: job_1494308265820_0005
17/05/09 07:19:31 INFO mapreduce.Job: Job job_1494308265820_0005 running in uber mode : false
17/05/09 07:19:31 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 07:19:44 INFO mapreduce.Job:  map 9% reduce 0%
17/05/09 07:19:47 INFO mapreduce.Job:  map 13% reduce 0%
17/05/09 07:19:50 INFO mapreduce.Job:  map 17% reduce 0%
17/05/09 07:19:53 INFO mapreduce.Job:  map 19% reduce 0%
17/05/09 07:19:56 INFO mapreduce.Job:  map 21% reduce 0%
17/05/09 07:19:59 INFO mapreduce.Job:  map 23% reduce 0%
17/05/09 07:20:03 INFO mapreduce.Job:  map 25% reduce 0%
17/05/09 07:20:06 INFO mapreduce.Job:  map 27% reduce 0%
17/05/09 07:20:09 INFO mapreduce.Job:  map 30% reduce 0%
17/05/09 07:20:12 INFO mapreduce.Job:  map 33% reduce 0%
17/05/09 07:20:15 INFO mapreduce.Job:  map 36% reduce 0%
17/05/09 07:20:18 INFO mapreduce.Job:  map 39% reduce 0%
17/05/09 07:20:21 INFO mapreduce.Job:  map 41% reduce 0%
17/05/09 07:20:24 INFO mapreduce.Job:  map 43% reduce 0%
17/05/09 07:20:27 INFO mapreduce.Job:  map 45% reduce 0%
17/05/09 07:20:30 INFO mapreduce.Job:  map 47% reduce 0%
17/05/09 07:20:33 INFO mapreduce.Job:  map 50% reduce 0%
17/05/09 07:20:36 INFO mapreduce.Job:  map 52% reduce 0%
17/05/09 07:20:39 INFO mapreduce.Job:  map 54% reduce 0%
17/05/09 07:20:42 INFO mapreduce.Job:  map 56% reduce 0%
17/05/09 07:20:45 INFO mapreduce.Job:  map 59% reduce 0%
17/05/09 07:20:48 INFO mapreduce.Job:  map 61% reduce 0%
17/05/09 07:20:51 INFO mapreduce.Job:  map 63% reduce 0%
17/05/09 07:20:54 INFO mapreduce.Job:  map 67% reduce 0%
17/05/09 07:20:57 INFO mapreduce.Job:  map 70% reduce 0%
17/05/09 07:21:01 INFO mapreduce.Job:  map 71% reduce 0%
17/05/09 07:21:04 INFO mapreduce.Job:  map 74% reduce 0%
17/05/09 07:21:07 INFO mapreduce.Job:  map 76% reduce 0%
17/05/09 07:21:10 INFO mapreduce.Job:  map 79% reduce 0%
17/05/09 07:21:13 INFO mapreduce.Job:  map 81% reduce 0%
17/05/09 07:21:15 INFO mapreduce.Job:  map 82% reduce 0%
17/05/09 07:21:16 INFO mapreduce.Job:  map 84% reduce 0%
17/05/09 07:21:18 INFO mapreduce.Job:  map 85% reduce 0%
17/05/09 07:21:19 INFO mapreduce.Job:  map 87% reduce 0%
17/05/09 07:21:21 INFO mapreduce.Job:  map 88% reduce 0%
17/05/09 07:21:22 INFO mapreduce.Job:  map 89% reduce 0%
17/05/09 07:21:24 INFO mapreduce.Job:  map 90% reduce 0%
17/05/09 07:21:25 INFO mapreduce.Job:  map 91% reduce 0%
17/05/09 07:21:27 INFO mapreduce.Job:  map 92% reduce 0%
17/05/09 07:21:28 INFO mapreduce.Job:  map 94% reduce 0%
17/05/09 07:21:31 INFO mapreduce.Job:  map 96% reduce 0%
17/05/09 07:21:34 INFO mapreduce.Job:  map 98% reduce 0%
17/05/09 07:21:35 INFO mapreduce.Job:  map 99% reduce 0%
17/05/09 07:21:36 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 07:21:37 INFO mapreduce.Job: Job job_1494308265820_0005 completed successfully
17/05/09 07:21:37 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=493200
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=487623
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=487623
		Total vcore-seconds taken by all map tasks=487623
		Total megabyte-seconds taken by all map tasks=499325952
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1969
		CPU time spent (ms)=171920
		Physical memory (bytes) snapshot=818176000
		Virtual memory (bytes) snapshot=6256570368
		Total committed heap usage (bytes)=824705024
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=230593859918397906
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10737418200

real	2m16.607s
user	0m5.924s
sys	0m0.743s
```

3.  Run the terasort command on this file  
Use the time command to report the job's duration  
Land the result under your user's home directory  
```
[hackty@ip-172-31-27-83 root]$ time hadoop jar /opt/cloudera/parcels/CDH-5.9.2-1.cdh5.9.2.p0.3/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapred.reduce.
tasks=50 /user/hackty/10g-input /user/hackty/10g-output17/05/09 07:58:33 INFO terasort.TeraSort: starting
17/05/09 07:58:35 INFO input.FileInputFormat: Total input paths to process : 4
Spent 289ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 296ms
Sampling 10 splits of 320
Making 50 from 100000 sampled records
Computing parititions took 978ms
Spent 1277ms computing partitions.
17/05/09 07:58:36 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-141.ec2.internal/172.31.17.141:8032
17/05/09 07:58:36 INFO mapreduce.JobSubmitter: number of splits:320
17/05/09 07:58:36 INFO Configuration.deprecation: mapred.reduce.tasks is deprecated. Instead, use mapreduce.job.reduces
17/05/09 07:58:37 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308265820_0006
17/05/09 07:58:37 INFO impl.YarnClientImpl: Submitted application application_1494308265820_0006
17/05/09 07:58:37 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-141.ec2.internal:8088/proxy/application_1494308265820_0006/
17/05/09 07:58:37 INFO mapreduce.Job: Running job: job_1494308265820_0006
17/05/09 07:58:44 INFO mapreduce.Job: Job job_1494308265820_0006 running in uber mode : false
17/05/09 07:58:44 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 07:58:53 INFO mapreduce.Job:  map 1% reduce 0%
17/05/09 07:58:55 INFO mapreduce.Job:  map 2% reduce 0%
17/05/09 07:58:56 INFO mapreduce.Job:  map 3% reduce 0%
17/05/09 07:58:59 INFO mapreduce.Job:  map 4% reduce 0%
17/05/09 07:59:04 INFO mapreduce.Job:  map 5% reduce 0%
17/05/09 07:59:06 INFO mapreduce.Job:  map 6% reduce 0%
17/05/09 07:59:10 INFO mapreduce.Job:  map 7% reduce 0%
17/05/09 07:59:11 INFO mapreduce.Job:  map 8% reduce 0%
17/05/09 07:59:15 INFO mapreduce.Job:  map 9% reduce 0%
17/05/09 07:59:17 INFO mapreduce.Job:  map 10% reduce 0%
17/05/09 07:59:18 INFO mapreduce.Job:  map 11% reduce 0%
17/05/09 07:59:25 INFO mapreduce.Job:  map 12% reduce 0%
17/05/09 07:59:26 INFO mapreduce.Job:  map 13% reduce 0%
17/05/09 07:59:28 INFO mapreduce.Job:  map 14% reduce 0%
17/05/09 07:59:35 INFO mapreduce.Job:  map 15% reduce 0%
17/05/09 07:59:36 INFO mapreduce.Job:  map 16% reduce 0%
17/05/09 07:59:38 INFO mapreduce.Job:  map 17% reduce 0%
17/05/09 07:59:40 INFO mapreduce.Job:  map 18% reduce 0%
17/05/09 07:59:44 INFO mapreduce.Job:  map 19% reduce 0%
17/05/09 07:59:47 INFO mapreduce.Job:  map 20% reduce 0%
17/05/09 07:59:51 INFO mapreduce.Job:  map 22% reduce 0%
17/05/09 07:59:54 INFO mapreduce.Job:  map 23% reduce 0%
17/05/09 07:59:59 INFO mapreduce.Job:  map 24% reduce 0%
17/05/09 08:00:02 INFO mapreduce.Job:  map 25% reduce 0%
17/05/09 08:00:04 INFO mapreduce.Job:  map 26% reduce 0%
17/05/09 08:00:05 INFO mapreduce.Job:  map 27% reduce 0%
17/05/09 08:00:07 INFO mapreduce.Job:  map 28% reduce 0%
17/05/09 08:00:13 INFO mapreduce.Job:  map 29% reduce 0%
17/05/09 08:00:15 INFO mapreduce.Job:  map 30% reduce 0%
17/05/09 08:00:16 INFO mapreduce.Job:  map 31% reduce 0%
17/05/09 08:00:19 INFO mapreduce.Job:  map 32% reduce 0%
17/05/09 08:00:24 INFO mapreduce.Job:  map 33% reduce 0%
17/05/09 08:00:25 INFO mapreduce.Job:  map 34% reduce 0%
17/05/09 08:00:30 INFO mapreduce.Job:  map 35% reduce 0%
17/05/09 08:00:32 INFO mapreduce.Job:  map 36% reduce 0%
17/05/09 08:00:35 INFO mapreduce.Job:  map 38% reduce 0%
17/05/09 08:00:40 INFO mapreduce.Job:  map 39% reduce 0%
17/05/09 08:00:44 INFO mapreduce.Job:  map 40% reduce 0%
17/05/09 08:00:45 INFO mapreduce.Job:  map 41% reduce 0%
17/05/09 08:00:46 INFO mapreduce.Job:  map 42% reduce 0%
17/05/09 08:00:50 INFO mapreduce.Job:  map 43% reduce 0%
17/05/09 08:00:55 INFO mapreduce.Job:  map 44% reduce 0%
17/05/09 08:00:57 INFO mapreduce.Job:  map 46% reduce 0%
17/05/09 08:01:03 INFO mapreduce.Job:  map 47% reduce 0%
17/05/09 08:01:05 INFO mapreduce.Job:  map 48% reduce 0%
17/05/09 08:01:08 INFO mapreduce.Job:  map 49% reduce 0%
17/05/09 08:01:11 INFO mapreduce.Job:  map 50% reduce 0%
17/05/09 08:01:14 INFO mapreduce.Job:  map 51% reduce 0%
17/05/09 08:01:15 INFO mapreduce.Job:  map 52% reduce 0%
17/05/09 08:01:19 INFO mapreduce.Job:  map 53% reduce 0%
17/05/09 08:01:23 INFO mapreduce.Job:  map 54% reduce 0%
17/05/09 08:01:25 INFO mapreduce.Job:  map 55% reduce 0%
17/05/09 08:01:28 INFO mapreduce.Job:  map 56% reduce 0%
17/05/09 08:01:30 INFO mapreduce.Job:  map 57% reduce 0%
17/05/09 08:01:35 INFO mapreduce.Job:  map 59% reduce 0%
17/05/09 08:01:38 INFO mapreduce.Job:  map 60% reduce 0%
17/05/09 08:01:41 INFO mapreduce.Job:  map 61% reduce 0%
17/05/09 08:01:44 INFO mapreduce.Job:  map 62% reduce 0%
17/05/09 08:01:46 INFO mapreduce.Job:  map 63% reduce 0%
17/05/09 08:01:50 INFO mapreduce.Job:  map 64% reduce 0%
17/05/09 08:01:52 INFO mapreduce.Job:  map 65% reduce 0%
17/05/09 08:01:55 INFO mapreduce.Job:  map 66% reduce 0%
17/05/09 08:01:58 INFO mapreduce.Job:  map 67% reduce 0%
17/05/09 08:02:00 INFO mapreduce.Job:  map 68% reduce 0%
17/05/09 08:02:04 INFO mapreduce.Job:  map 69% reduce 0%
17/05/09 08:02:08 INFO mapreduce.Job:  map 70% reduce 0%
17/05/09 08:02:09 INFO mapreduce.Job:  map 71% reduce 0%
17/05/09 08:02:13 INFO mapreduce.Job:  map 72% reduce 0%
17/05/09 08:02:14 INFO mapreduce.Job:  map 73% reduce 0%
17/05/09 08:02:17 INFO mapreduce.Job:  map 74% reduce 0%
17/05/09 08:02:21 INFO mapreduce.Job:  map 75% reduce 0%
17/05/09 08:02:25 INFO mapreduce.Job:  map 76% reduce 0%
17/05/09 08:02:26 INFO mapreduce.Job:  map 77% reduce 0%
17/05/09 08:02:28 INFO mapreduce.Job:  map 78% reduce 0%
17/05/09 08:02:33 INFO mapreduce.Job:  map 79% reduce 0%
17/05/09 08:02:35 INFO mapreduce.Job:  map 80% reduce 0%
17/05/09 08:02:38 INFO mapreduce.Job:  map 81% reduce 0%
17/05/09 08:02:40 INFO mapreduce.Job:  map 82% reduce 0%
17/05/09 08:02:43 INFO mapreduce.Job:  map 83% reduce 0%
17/05/09 08:02:46 INFO mapreduce.Job:  map 84% reduce 0%
17/05/09 08:02:48 INFO mapreduce.Job:  map 85% reduce 0%
17/05/09 08:02:52 INFO mapreduce.Job:  map 85% reduce 1%
17/05/09 08:02:55 INFO mapreduce.Job:  map 86% reduce 2%
17/05/09 08:02:56 INFO mapreduce.Job:  map 86% reduce 3%
17/05/09 08:02:59 INFO mapreduce.Job:  map 86% reduce 4%
17/05/09 08:03:00 INFO mapreduce.Job:  map 87% reduce 4%
17/05/09 08:03:02 INFO mapreduce.Job:  map 88% reduce 4%
17/05/09 08:03:08 INFO mapreduce.Job:  map 89% reduce 4%
17/05/09 08:03:14 INFO mapreduce.Job:  map 90% reduce 4%
17/05/09 08:03:16 INFO mapreduce.Job:  map 91% reduce 4%
17/05/09 08:03:20 INFO mapreduce.Job:  map 92% reduce 4%
17/05/09 08:03:26 INFO mapreduce.Job:  map 93% reduce 4%
17/05/09 08:03:31 INFO mapreduce.Job:  map 94% reduce 4%
17/05/09 08:03:34 INFO mapreduce.Job:  map 95% reduce 4%
17/05/09 08:03:39 INFO mapreduce.Job:  map 96% reduce 4%
17/05/09 08:03:43 INFO mapreduce.Job:  map 97% reduce 4%
17/05/09 08:03:44 INFO mapreduce.Job:  map 97% reduce 5%
17/05/09 08:03:47 INFO mapreduce.Job:  map 98% reduce 5%
17/05/09 08:03:52 INFO mapreduce.Job:  map 99% reduce 5%
17/05/09 08:03:56 INFO mapreduce.Job:  map 100% reduce 5%
17/05/09 08:04:02 INFO mapreduce.Job:  map 100% reduce 7%
17/05/09 08:04:03 INFO mapreduce.Job:  map 100% reduce 8%
17/05/09 08:04:04 INFO mapreduce.Job:  map 100% reduce 11%
17/05/09 08:04:05 INFO mapreduce.Job:  map 100% reduce 12%
17/05/09 08:04:06 INFO mapreduce.Job:  map 100% reduce 14%
17/05/09 08:04:07 INFO mapreduce.Job:  map 100% reduce 17%
17/05/09 08:04:08 INFO mapreduce.Job:  map 100% reduce 18%
17/05/09 08:04:09 INFO mapreduce.Job:  map 100% reduce 19%
17/05/09 08:04:10 INFO mapreduce.Job:  map 100% reduce 20%
17/05/09 08:04:11 INFO mapreduce.Job:  map 100% reduce 21%
17/05/09 08:04:13 INFO mapreduce.Job:  map 100% reduce 22%
17/05/09 08:04:14 INFO mapreduce.Job:  map 100% reduce 23%
17/05/09 08:04:18 INFO mapreduce.Job:  map 100% reduce 25%
17/05/09 08:04:19 INFO mapreduce.Job:  map 100% reduce 26%
17/05/09 08:04:21 INFO mapreduce.Job:  map 100% reduce 28%
17/05/09 08:04:22 INFO mapreduce.Job:  map 100% reduce 30%
17/05/09 08:04:23 INFO mapreduce.Job:  map 100% reduce 32%
17/05/09 08:04:24 INFO mapreduce.Job:  map 100% reduce 35%
17/05/09 08:04:25 INFO mapreduce.Job:  map 100% reduce 36%
17/05/09 08:04:26 INFO mapreduce.Job:  map 100% reduce 37%
17/05/09 08:04:27 INFO mapreduce.Job:  map 100% reduce 38%
17/05/09 08:04:28 INFO mapreduce.Job:  map 100% reduce 41%
17/05/09 08:04:30 INFO mapreduce.Job:  map 100% reduce 42%
17/05/09 08:04:31 INFO mapreduce.Job:  map 100% reduce 43%
17/05/09 08:04:32 INFO mapreduce.Job:  map 100% reduce 44%
17/05/09 08:04:34 INFO mapreduce.Job:  map 100% reduce 47%
17/05/09 08:04:37 INFO mapreduce.Job:  map 100% reduce 49%
17/05/09 08:04:38 INFO mapreduce.Job:  map 100% reduce 50%
17/05/09 08:04:39 INFO mapreduce.Job:  map 100% reduce 52%
17/05/09 08:04:41 INFO mapreduce.Job:  map 100% reduce 54%
17/05/09 08:04:42 INFO mapreduce.Job:  map 100% reduce 55%
17/05/09 08:04:43 INFO mapreduce.Job:  map 100% reduce 56%
17/05/09 08:04:44 INFO mapreduce.Job:  map 100% reduce 58%
17/05/09 08:04:45 INFO mapreduce.Job:  map 100% reduce 60%
17/05/09 08:04:46 INFO mapreduce.Job:  map 100% reduce 61%
17/05/09 08:04:48 INFO mapreduce.Job:  map 100% reduce 63%
17/05/09 08:04:49 INFO mapreduce.Job:  map 100% reduce 64%
17/05/09 08:04:50 INFO mapreduce.Job:  map 100% reduce 65%
17/05/09 08:04:51 INFO mapreduce.Job:  map 100% reduce 67%
17/05/09 08:04:54 INFO mapreduce.Job:  map 100% reduce 70%
17/05/09 08:04:57 INFO mapreduce.Job:  map 100% reduce 72%
17/05/09 08:04:58 INFO mapreduce.Job:  map 100% reduce 73%
17/05/09 08:05:00 INFO mapreduce.Job:  map 100% reduce 74%
17/05/09 08:05:02 INFO mapreduce.Job:  map 100% reduce 76%
17/05/09 08:05:04 INFO mapreduce.Job:  map 100% reduce 83%
17/05/09 08:05:06 INFO mapreduce.Job:  map 100% reduce 84%
17/05/09 08:05:07 INFO mapreduce.Job:  map 100% reduce 88%
17/05/09 08:05:09 INFO mapreduce.Job:  map 100% reduce 89%
17/05/09 08:05:10 INFO mapreduce.Job:  map 100% reduce 91%
17/05/09 08:05:12 INFO mapreduce.Job:  map 100% reduce 92%
17/05/09 08:05:16 INFO mapreduce.Job:  map 100% reduce 93%
17/05/09 08:05:18 INFO mapreduce.Job:  map 100% reduce 95%
17/05/09 08:05:19 INFO mapreduce.Job:  map 100% reduce 97%
17/05/09 08:05:20 INFO mapreduce.Job:  map 100% reduce 99%
17/05/09 08:05:21 INFO mapreduce.Job:  map 100% reduce 100%
17/05/09 08:05:23 INFO mapreduce.Job: Job job_1494308265820_0006 completed successfully
17/05/09 08:05:23 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4791439228
		FILE: Number of bytes written=9536373381
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10737463320
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=1110
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=100
	Job Counters 
		Launched map tasks=320
		Launched reduce tasks=50
		Data-local map tasks=320
		Total time spent by all maps in occupied slots (ms)=2869920
		Total time spent by all reduces in occupied slots (ms)=1397060
		Total time spent by all map tasks (ms)=2869920
		Total time spent by all reduce tasks (ms)=1397060
		Total vcore-seconds taken by all map tasks=2869920
		Total vcore-seconds taken by all reduce tasks=1397060
		Total megabyte-seconds taken by all map tasks=2938798080
		Total megabyte-seconds taken by all reduce tasks=1430589440
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Map output bytes=10952166564
		Map output materialized bytes=4698587943
		Input split bytes=45120
		Combine input records=0
		Combine output records=0
		Reduce input groups=107374182
		Reduce shuffle bytes=4698587943
		Reduce input records=107374182
		Reduce output records=107374182
		Spilled Records=214748364
		Shuffled Maps =16000
		Failed Shuffles=0
		Merged Map outputs=16000
		GC time elapsed (ms)=55796
		CPU time spent (ms)=1922930
		Physical memory (bytes) snapshot=181009641472
		Virtual memory (bytes) snapshot=579290730496
		Total committed heap usage (bytes)=201911173120
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10737418200
	File Output Format Counters 
		Bytes Written=10737418200
17/05/09 08:05:23 INFO terasort.TeraSort: done

real	6m50.905s
user	0m9.828s
sys	0m1.087s
```
