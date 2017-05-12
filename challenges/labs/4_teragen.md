<html>
<h3>The full teragen command and job output<h3>
<pre>
[zhou@p1 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Ddfs.blocksize=67108864 -Dmapreduce.job.maps=6 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819  65536000 tgen
17/05/12 03:50:27 INFO client.RMProxy: Connecting to ResourceManager at p1/172.31.9.183:8032
17/05/12 03:50:28 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 03:50:28 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 03:50:28 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494558836547_0001
17/05/12 03:50:29 INFO impl.YarnClientImpl: Submitted application application_1494558836547_0001
17/05/12 03:50:29 INFO mapreduce.Job: The url to track the job: http://p1:8088/proxy/application_1494558836547_0001/
17/05/12 03:50:29 INFO mapreduce.Job: Running job: job_1494558836547_0001
17/05/12 03:50:36 INFO mapreduce.Job: Job job_1494558836547_0001 running in uber mode : false
17/05/12 03:50:36 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 03:50:53 INFO mapreduce.Job:  map 13% reduce 0%
17/05/12 03:50:56 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 03:50:59 INFO mapreduce.Job:  map 27% reduce 0%
17/05/12 03:51:02 INFO mapreduce.Job:  map 33% reduce 0%
17/05/12 03:51:05 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 03:51:08 INFO mapreduce.Job:  map 40% reduce 0%
17/05/12 03:51:11 INFO mapreduce.Job:  map 45% reduce 0%
17/05/12 03:51:14 INFO mapreduce.Job:  map 49% reduce 0%
17/05/12 03:51:17 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 03:51:20 INFO mapreduce.Job:  map 55% reduce 0%
17/05/12 03:51:23 INFO mapreduce.Job:  map 59% reduce 0%
17/05/12 03:51:26 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 03:51:29 INFO mapreduce.Job:  map 69% reduce 0%
17/05/12 03:51:32 INFO mapreduce.Job:  map 73% reduce 0%
17/05/12 03:51:35 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 03:51:38 INFO mapreduce.Job:  map 80% reduce 0%
17/05/12 03:51:41 INFO mapreduce.Job:  map 83% reduce 0%
17/05/12 03:51:44 INFO mapreduce.Job:  map 86% reduce 0%
17/05/12 03:51:47 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 03:51:50 INFO mapreduce.Job:  map 92% reduce 0%
17/05/12 03:51:53 INFO mapreduce.Job:  map 95% reduce 0%
17/05/12 03:51:55 INFO mapreduce.Job:  map 96% reduce 0%
17/05/12 03:51:56 INFO mapreduce.Job:  map 98% reduce 0%
17/05/12 03:51:58 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 03:51:58 INFO mapreduce.Job: Job job_1494558836547_0001 completed successfully
17/05/12 03:51:58 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=737844
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
		Total time spent by all maps in occupied slots (ms)=457774
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=457774
		Total vcore-seconds taken by all map tasks=457774
		Total megabyte-seconds taken by all map tasks=468760576
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=511
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1533
		CPU time spent (ms)=126410
		Physical memory (bytes) snapshot=2046111744
		Virtual memory (bytes) snapshot=9383321600
		Total committed heap usage (bytes)=2025848832
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=6553600000
</pre>

<h3>The result of the time command</h3>
<pre>
real	1m33.928s
user	0m6.399s
sys	0m0.735s
</pre>


<h3>The command and output of hdfs dfs -ls /user/zhou/tgen<h3>
<pre>
[zhou@p1 ~]$ hdfs dfs -ls /user/zhou/tgen
Found 7 items
-rw-r--r--   3 zhou zhou          0 2017-05-12 03:51 /user/zhou/tgen/_SUCCESS
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 03:51 /user/zhou/tgen/part-m-00000
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 03:51 /user/zhou/tgen/part-m-00001
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 03:51 /user/zhou/tgen/part-m-00002
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 03:51 /user/zhou/tgen/part-m-00003
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 03:51 /user/zhou/tgen/part-m-00004
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 03:51 /user/zhou/tgen/part-m-00005
</pre>
</html>
