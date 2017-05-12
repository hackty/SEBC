# The full teragen command and job output
```
[zhou@ip-172-31-17-205 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.map.memory.mb=1024 -Dmapred.map
.tasks=6 -Ddfs.block.size=67108864 65536000 /user/zhou/tgen17/05/12 02:28:31 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-205.ec2.internal/172.31.17.205:8032
17/05/12 02:28:31 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 02:28:31 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 02:28:31 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/12 02:28:31 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/05/12 02:28:32 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494555440013_0001
17/05/12 02:28:32 INFO impl.YarnClientImpl: Submitted application application_1494555440013_0001
17/05/12 02:28:32 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-205.ec2.internal:8088/proxy/application_1494555440013_0001/
17/05/12 02:28:32 INFO mapreduce.Job: Running job: job_1494555440013_0001
17/05/12 02:28:39 INFO mapreduce.Job: Job job_1494555440013_0001 running in uber mode : false
17/05/12 02:28:39 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 02:28:51 INFO mapreduce.Job:  map 5% reduce 0%
17/05/12 02:28:53 INFO mapreduce.Job:  map 8% reduce 0%
17/05/12 02:28:54 INFO mapreduce.Job:  map 14% reduce 0%
17/05/12 02:28:55 INFO mapreduce.Job:  map 19% reduce 0%
17/05/12 02:28:56 INFO mapreduce.Job:  map 21% reduce 0%
17/05/12 02:28:58 INFO mapreduce.Job:  map 26% reduce 0%
17/05/12 02:28:59 INFO mapreduce.Job:  map 27% reduce 0%
17/05/12 02:29:01 INFO mapreduce.Job:  map 33% reduce 0%
17/05/12 02:29:02 INFO mapreduce.Job:  map 34% reduce 0%
17/05/12 02:29:04 INFO mapreduce.Job:  map 38% reduce 0%
17/05/12 02:29:05 INFO mapreduce.Job:  map 39% reduce 0%
17/05/12 02:29:07 INFO mapreduce.Job:  map 43% reduce 0%
17/05/12 02:29:10 INFO mapreduce.Job:  map 47% reduce 0%
17/05/12 02:29:13 INFO mapreduce.Job:  map 51% reduce 0%
17/05/12 02:29:14 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 02:29:16 INFO mapreduce.Job:  map 55% reduce 0%
17/05/12 02:29:17 INFO mapreduce.Job:  map 56% reduce 0%
17/05/12 02:29:19 INFO mapreduce.Job:  map 59% reduce 0%
17/05/12 02:29:20 INFO mapreduce.Job:  map 60% reduce 0%
17/05/12 02:29:22 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 02:29:23 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 02:29:25 INFO mapreduce.Job:  map 67% reduce 0%
17/05/12 02:29:26 INFO mapreduce.Job:  map 68% reduce 0%
17/05/12 02:29:28 INFO mapreduce.Job:  map 71% reduce 0%
17/05/12 02:29:29 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 02:29:31 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 02:29:32 INFO mapreduce.Job:  map 76% reduce 0%
17/05/12 02:29:34 INFO mapreduce.Job:  map 79% reduce 0%
17/05/12 02:29:37 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 02:29:39 INFO mapreduce.Job:  map 84% reduce 0%
17/05/12 02:29:40 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 02:29:43 INFO mapreduce.Job:  map 93% reduce 0%
17/05/12 02:29:46 INFO mapreduce.Job:  map 96% reduce 0%
17/05/12 02:29:49 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 02:29:50 INFO mapreduce.Job: Job job_1494555440013_0001 completed successfully
17/05/12 02:29:51 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=739722
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=511
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=24
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters 
		Launched map tasks=6
		Other local map tasks=6
		Total time spent by all maps in occupied slots (ms)=382022
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=382022
		Total vcore-seconds taken by all map tasks=382022
		Total megabyte-seconds taken by all map tasks=391190528
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=511
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1047
		CPU time spent (ms)=123110
		Physical memory (bytes) snapshot=1944887296
		Virtual memory (bytes) snapshot=9342357504
		Total committed heap usage (bytes)=1924661248
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	1m23.125s
user	0m5.988s
sys	0m0.790s
```

# The result of the time command
```
real	1m23.125s
user	0m5.988s
sys	0m0.790s
```

# The command and output of hdfs dfs -ls /user/zhou/tgen
```
[zhou@ip-172-31-17-205 ~]$ hdfs dfs -ls /user/zhou/tgen
Found 7 items
-rw-r--r--   3 zhou zhou          0 2017-05-12 02:29 /user/zhou/tgen/_SUCCESS
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:29 /user/zhou/tgen/part-m-00000
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:29 /user/zhou/tgen/part-m-00001
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 02:29 /user/zhou/tgen/part-m-00002
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:29 /user/zhou/tgen/part-m-00003
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:29 /user/zhou/tgen/part-m-00004
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 02:29 /user/zhou/tgen/part-m-00005
```
