The full teragen command and output

```
[ec2-user@ip-172-31-8-180 ~]$ sudo -u saturn time hadoop jar /opt/cloudera/parcels/CDH-5.10.2-1.cdh5.10.2.p0.5/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=12 -Ddfs.blocksize=33554432 -Dmapreduce.map.memory.mb=512 -Dyarn.app.mapreduce.am.containerlauncher.threadpool-initial-size=512 65536000 /user/saturn/tgen
18/01/05 11:25:24 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-8-180.us-west-2.compute.internal/172.31.8.180:8032
18/01/05 11:25:25 INFO terasort.TeraGen: Generating 65536000 using 12
18/01/05 11:25:25 INFO mapreduce.JobSubmitter: number of splits:12
18/01/05 11:25:25 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1515168113107_0001
18/01/05 11:25:25 INFO impl.YarnClientImpl: Submitted application application_1515168113107_0001
18/01/05 11:25:25 INFO mapreduce.Job: The url to track the job: http://ip-172-31-8-180.us-west-2.compute.internal:8088/proxy/application_1515168113107_0001/
18/01/05 11:25:25 INFO mapreduce.Job: Running job: job_1515168113107_0001
18/01/05 11:25:33 INFO mapreduce.Job: Job job_1515168113107_0001 running in uber mode : false
18/01/05 11:25:33 INFO mapreduce.Job:  map 0% reduce 0%
18/01/05 11:25:51 INFO mapreduce.Job:  map 7% reduce 0%
18/01/05 11:25:52 INFO mapreduce.Job:  map 18% reduce 0%
18/01/05 11:25:53 INFO mapreduce.Job:  map 24% reduce 0%
18/01/05 11:25:54 INFO mapreduce.Job:  map 29% reduce 0%
18/01/05 11:25:55 INFO mapreduce.Job:  map 31% reduce 0%
18/01/05 11:25:57 INFO mapreduce.Job:  map 33% reduce 0%
18/01/05 11:25:58 INFO mapreduce.Job:  map 36% reduce 0%
18/01/05 11:25:59 INFO mapreduce.Job:  map 38% reduce 0%
18/01/05 11:26:00 INFO mapreduce.Job:  map 40% reduce 0%
18/01/05 11:26:02 INFO mapreduce.Job:  map 41% reduce 0%
18/01/05 11:26:04 INFO mapreduce.Job:  map 43% reduce 0%
18/01/05 11:26:05 INFO mapreduce.Job:  map 45% reduce 0%
18/01/05 11:26:06 INFO mapreduce.Job:  map 46% reduce 0%
18/01/05 11:26:08 INFO mapreduce.Job:  map 47% reduce 0%
18/01/05 11:26:09 INFO mapreduce.Job:  map 48% reduce 0%
18/01/05 11:26:11 INFO mapreduce.Job:  map 50% reduce 0%
18/01/05 11:26:12 INFO mapreduce.Job:  map 51% reduce 0%
18/01/05 11:26:13 INFO mapreduce.Job:  map 53% reduce 0%
18/01/05 11:26:15 INFO mapreduce.Job:  map 54% reduce 0%
18/01/05 11:26:16 INFO mapreduce.Job:  map 56% reduce 0%
18/01/05 11:26:17 INFO mapreduce.Job:  map 57% reduce 0%
18/01/05 11:26:18 INFO mapreduce.Job:  map 59% reduce 0%
18/01/05 11:26:19 INFO mapreduce.Job:  map 60% reduce 0%
18/01/05 11:26:21 INFO mapreduce.Job:  map 61% reduce 0%
18/01/05 11:26:22 INFO mapreduce.Job:  map 63% reduce 0%
18/01/05 11:26:23 INFO mapreduce.Job:  map 64% reduce 0%
18/01/05 11:26:24 INFO mapreduce.Job:  map 66% reduce 0%
18/01/05 11:26:25 INFO mapreduce.Job:  map 67% reduce 0%
18/01/05 11:26:27 INFO mapreduce.Job:  map 68% reduce 0%
18/01/05 11:26:28 INFO mapreduce.Job:  map 70% reduce 0%
18/01/05 11:26:30 INFO mapreduce.Job:  map 72% reduce 0%
18/01/05 11:26:33 INFO mapreduce.Job:  map 73% reduce 0%
18/01/05 11:26:34 INFO mapreduce.Job:  map 75% reduce 0%
18/01/05 11:26:35 INFO mapreduce.Job:  map 76% reduce 0%
18/01/05 11:26:36 INFO mapreduce.Job:  map 78% reduce 0%
18/01/05 11:26:39 INFO mapreduce.Job:  map 79% reduce 0%
18/01/05 11:26:41 INFO mapreduce.Job:  map 82% reduce 0%
18/01/05 11:26:42 INFO mapreduce.Job:  map 83% reduce 0%
18/01/05 11:26:43 INFO mapreduce.Job:  map 85% reduce 0%
18/01/05 11:26:47 INFO mapreduce.Job:  map 87% reduce 0%
18/01/05 11:26:48 INFO mapreduce.Job:  map 90% reduce 0%
18/01/05 11:26:49 INFO mapreduce.Job:  map 92% reduce 0%
18/01/05 11:26:50 INFO mapreduce.Job:  map 93% reduce 0%
18/01/05 11:26:53 INFO mapreduce.Job:  map 94% reduce 0%
18/01/05 11:26:54 INFO mapreduce.Job:  map 96% reduce 0%
18/01/05 11:26:55 INFO mapreduce.Job:  map 99% reduce 0%
18/01/05 11:26:57 INFO mapreduce.Job:  map 100% reduce 0%
18/01/05 11:26:57 INFO mapreduce.Job: Job job_1515168113107_0001 completed successfully
18/01/05 11:26:57 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1500674
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=920295
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=920295
                Total vcore-seconds taken by all map tasks=920295
                Total megabyte-seconds taken by all map tasks=942382080
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1830
                CPU time spent (ms)=157240
                Physical memory (bytes) snapshot=2468900864
                Virtual memory (bytes) snapshot=13782700032
                Total committed heap usage (bytes)=4481613824
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
5.34user 0.32system 1:35.55elapsed 5%CPU (0avgtext+0avgdata 236088maxresident)k
0inputs+1088outputs (0major+75180minor)pagefaults 0swaps


```

The result of the time command

```

[ec2-user@ip-172-31-8-180 /]$ time

real    0m0.000s
user    0m0.000s
sys     0m0.000s

```


The command and output of hdfs dfs -ls /user/saturn/tgen

```

[ec2-user@ip-172-31-8-180 /]$ hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn planets          0 2018-01-05 11:26 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn planets  546133400 2018-01-05 11:26 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn planets  546133400 2018-01-05 11:26 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn planets  546133400 2018-01-05 11:26 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn planets  546133400 2018-01-05 11:26 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn planets  546133300 2018-01-05 11:26 /user/saturn/tgen/part-m-00011
[ec2-user@ip-172-31-8-180 /]$

```


The command and output of hadoop fsck -blocks /user/saturn


```
[ec2-user@ip-172-31-8-180 /]$ sudo -u hdfs hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-8-180.us-west-2.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.8.180 for path /user/saturn at Fri Jan 05 11:33:15 EST 2018
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Jan 05 11:33:15 EST 2018 in 11 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
[ec2-user@ip-172-31-8-180 /]$


```
