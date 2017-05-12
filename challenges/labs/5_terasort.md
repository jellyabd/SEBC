<html>
<pre>
[root@p1 kk]# kinit zhou
Password for zhou@WHITELILIS.CN:
[root@p1 kk]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Ddfs.blocksize=67108864 -Dmapreduce.job.maps=6 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819  65536000 tsort
17/05/12 04:36:42 INFO client.RMProxy: Connecting to ResourceManager at p1/172.31.9.183:8032
17/05/12 04:36:42 INFO hdfs.DFSClient: Created token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@WHITELILIS.CN, renewer=yarn, realUser=, issueDate=1494563802443, maxDate=1495168602443, sequenceNumber=1, masterKeyId=2 on 172.31.9.183:8020
17/05/12 04:36:42 INFO security.TokenCache: Got dt for hdfs://p1:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.9.183:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@WHITELILIS.CN, renewer=yarn, realUser=, issueDate=1494563802443, maxDate=1495168602443, sequenceNumber=1, masterKeyId=2)
17/05/12 04:36:42 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 04:36:42 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 04:36:43 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494563033313_0001
17/05/12 04:36:43 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.9.183:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@WHITELILIS.CN, renewer=yarn, realUser=, issueDate=1494563802443, maxDate=1495168602443, sequenceNumber=1, masterKeyId=2)
17/05/12 04:36:44 INFO impl.YarnClientImpl: Submitted application application_1494563033313_0001
17/05/12 04:36:44 INFO mapreduce.Job: The url to track the job: http://p1:8088/proxy/application_1494563033313_0001/
17/05/12 04:36:44 INFO mapreduce.Job: Running job: job_1494563033313_0001
17/05/12 04:36:55 INFO mapreduce.Job: Job job_1494563033313_0001 running in uber mode : false
17/05/12 04:36:55 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 04:37:14 INFO mapreduce.Job:  map 2% reduce 0%
17/05/12 04:37:15 INFO mapreduce.Job:  map 12% reduce 0%
17/05/12 04:37:18 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 04:37:21 INFO mapreduce.Job:  map 25% reduce 0%
17/05/12 04:37:24 INFO mapreduce.Job:  map 30% reduce 0%
17/05/12 04:37:28 INFO mapreduce.Job:  map 34% reduce 0%
17/05/12 04:37:31 INFO mapreduce.Job:  map 38% reduce 0%
17/05/12 04:37:34 INFO mapreduce.Job:  map 42% reduce 0%
17/05/12 04:37:37 INFO mapreduce.Job:  map 46% reduce 0%
17/05/12 04:37:40 INFO mapreduce.Job:  map 50% reduce 0%
17/05/12 04:37:43 INFO mapreduce.Job:  map 53% reduce 0%
17/05/12 04:37:46 INFO mapreduce.Job:  map 56% reduce 0%
17/05/12 04:37:49 INFO mapreduce.Job:  map 59% reduce 0%
17/05/12 04:37:52 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 04:37:53 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 04:37:55 INFO mapreduce.Job:  map 66% reduce 0%
17/05/12 04:37:56 INFO mapreduce.Job:  map 67% reduce 0%
17/05/12 04:37:58 INFO mapreduce.Job:  map 70% reduce 0%
17/05/12 04:37:59 INFO mapreduce.Job:  map 71% reduce 0%
17/05/12 04:38:01 INFO mapreduce.Job:  map 73% reduce 0%
17/05/12 04:38:02 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 04:38:04 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 04:38:05 INFO mapreduce.Job:  map 78% reduce 0%
17/05/12 04:38:07 INFO mapreduce.Job:  map 81% reduce 0%
17/05/12 04:38:08 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 04:38:10 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 04:38:11 INFO mapreduce.Job:  map 86% reduce 0%
17/05/12 04:38:13 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 04:38:14 INFO mapreduce.Job:  map 90% reduce 0%
17/05/12 04:38:16 INFO mapreduce.Job:  map 91% reduce 0%
17/05/12 04:38:17 INFO mapreduce.Job:  map 94% reduce 0%
17/05/12 04:38:19 INFO mapreduce.Job:  map 95% reduce 0%
17/05/12 04:38:20 INFO mapreduce.Job:  map 97% reduce 0%
17/05/12 04:38:22 INFO mapreduce.Job:  map 99% reduce 0%
17/05/12 04:38:23 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 04:38:23 INFO mapreduce.Job: Job job_1494563033313_0001 completed successfully
17/05/12 04:38:23 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=742398
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
		Total time spent by all maps in occupied slots (ms)=505196
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=505196
		Total vcore-seconds taken by all map tasks=505196
		Total megabyte-seconds taken by all map tasks=517320704
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=511
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1490
		CPU time spent (ms)=125230
		Physical memory (bytes) snapshot=2001600512
		Virtual memory (bytes) snapshot=9344847872
		Total committed heap usage (bytes)=2040528896
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=6553600000

real	1m44.565s
user	0m6.394s
sys	0m0.736s
</pre>
</html>
