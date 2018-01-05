Run the terasort program as user saturn with the output target /user/saturn/tsort
Generate 10,000,000 records

Copy the command and full output 


```
[ec2-user@ip-172-31-7-166 ~]$ time hadoop jar /logdisk/opt/cloudera/parcels/CDH-5.10.2-1.cdh5.10.2.p0.5/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -D mapred.reduce.tasks=6 /user/saturn/tgen /user/saturn/tsort
18/01/05 12:02:28 INFO terasort.TeraSort: starting
18/01/05 12:02:30 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@FRANZANTEJM.HQ, renewer=yarn, realUser=, issueDate=1515171750123, maxDate=1515776550123, sequenceNumber=2, masterKeyId=2 on 172.31.8.180:8020
18/01/05 12:02:30 INFO security.TokenCache: Got dt for hdfs://ip-172-31-8-180.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.8.180:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@FRANZANTEJM.HQ, renewer=yarn, realUser=, issueDate=1515171750123, maxDate=1515776550123, sequenceNumber=2, masterKeyId=2)
18/01/05 12:02:30 INFO input.FileInputFormat: Total input paths to process : 12
Spent 369ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 373ms
Sampling 10 splits of 204
Making 6 from 100000 sampled records
Computing parititions took 624ms
Spent 1000ms computing partitions.
18/01/05 12:02:31 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-8-180.us-west-2.compute.internal/172.31.8.180:8032
18/01/05 12:02:31 INFO mapreduce.JobSubmitter: number of splits:204
18/01/05 12:02:31 INFO Configuration.deprecation: mapred.reduce.tasks is deprecated. Instead, use mapreduce.job.reduces
18/01/05 12:02:31 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1515171482176_0002
18/01/05 12:02:31 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.8.180:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@FRANZANTEJM.HQ, renewer=yarn, realUser=, issueDate=1515171750123, maxDate=1515776550123, sequenceNumber=2, masterKeyId=2)
18/01/05 12:02:31 INFO impl.YarnClientImpl: Submitted application application_1515171482176_0002
18/01/05 12:02:31 INFO mapreduce.Job: The url to track the job: http://ip-172-31-8-180.us-west-2.compute.internal:8088/proxy/application_1515171482176_0002/
18/01/05 12:02:31 INFO mapreduce.Job: Running job: job_1515171482176_0002
18/01/05 12:02:41 INFO mapreduce.Job: Job job_1515171482176_0002 running in uber mode : false
18/01/05 12:02:41 INFO mapreduce.Job:  map 0% reduce 0%
18/01/05 12:02:51 INFO mapreduce.Job:  map 3% reduce 0%
18/01/05 12:02:52 INFO mapreduce.Job:  map 4% reduce 0%
18/01/05 12:02:58 INFO mapreduce.Job:  map 5% reduce 0%
18/01/05 12:03:00 INFO mapreduce.Job:  map 9% reduce 0%
18/01/05 12:03:01 INFO mapreduce.Job:  map 12% reduce 0%
18/01/05 12:03:06 INFO mapreduce.Job:  map 13% reduce 0%
18/01/05 12:03:10 INFO mapreduce.Job:  map 15% reduce 0%
18/01/05 12:03:11 INFO mapreduce.Job:  map 16% reduce 0%
18/01/05 12:03:13 INFO mapreduce.Job:  map 17% reduce 0%
18/01/05 12:03:14 INFO mapreduce.Job:  map 19% reduce 0%
18/01/05 12:03:15 INFO mapreduce.Job:  map 20% reduce 0%
18/01/05 12:03:16 INFO mapreduce.Job:  map 21% reduce 0%
18/01/05 12:03:19 INFO mapreduce.Job:  map 23% reduce 0%
18/01/05 12:03:20 INFO mapreduce.Job:  map 25% reduce 0%
18/01/05 12:03:27 INFO mapreduce.Job:  map 27% reduce 0%
18/01/05 12:03:28 INFO mapreduce.Job:  map 30% reduce 0%
18/01/05 12:03:29 INFO mapreduce.Job:  map 33% reduce 0%
18/01/05 12:03:34 INFO mapreduce.Job:  map 34% reduce 0%
18/01/05 12:03:37 INFO mapreduce.Job:  map 36% reduce 0%
18/01/05 12:03:38 INFO mapreduce.Job:  map 37% reduce 0%
18/01/05 12:03:40 INFO mapreduce.Job:  map 38% reduce 0%
18/01/05 12:03:41 INFO mapreduce.Job:  map 41% reduce 0%
18/01/05 12:03:42 INFO mapreduce.Job:  map 42% reduce 0%
18/01/05 12:03:46 INFO mapreduce.Job:  map 44% reduce 0%
18/01/05 12:03:47 INFO mapreduce.Job:  map 45% reduce 0%
18/01/05 12:03:48 INFO mapreduce.Job:  map 46% reduce 0%
18/01/05 12:03:52 INFO mapreduce.Job:  map 47% reduce 0%
18/01/05 12:03:55 INFO mapreduce.Job:  map 52% reduce 0%
18/01/05 12:03:56 INFO mapreduce.Job:  map 54% reduce 0%
18/01/05 12:04:02 INFO mapreduce.Job:  map 55% reduce 0%
18/01/05 12:04:04 INFO mapreduce.Job:  map 56% reduce 0%
18/01/05 12:04:06 INFO mapreduce.Job:  map 59% reduce 0%
18/01/05 12:04:09 INFO mapreduce.Job:  map 60% reduce 0%
18/01/05 12:04:10 INFO mapreduce.Job:  map 63% reduce 0%
18/01/05 12:04:13 INFO mapreduce.Job:  map 64% reduce 0%
18/01/05 12:04:14 INFO mapreduce.Job:  map 65% reduce 0%
18/01/05 12:04:15 INFO mapreduce.Job:  map 66% reduce 0%
18/01/05 12:04:16 INFO mapreduce.Job:  map 67% reduce 0%
18/01/05 12:04:17 INFO mapreduce.Job:  map 68% reduce 0%
18/01/05 12:04:21 INFO mapreduce.Job:  map 69% reduce 0%
18/01/05 12:04:22 INFO mapreduce.Job:  map 70% reduce 0%
18/01/05 12:04:23 INFO mapreduce.Job:  map 74% reduce 0%
18/01/05 12:04:24 INFO mapreduce.Job:  map 75% reduce 0%
18/01/05 12:04:30 INFO mapreduce.Job:  map 77% reduce 0%
18/01/05 12:04:31 INFO mapreduce.Job:  map 78% reduce 0%
18/01/05 12:04:33 INFO mapreduce.Job:  map 80% reduce 0%
18/01/05 12:04:36 INFO mapreduce.Job:  map 81% reduce 0%
18/01/05 12:04:37 INFO mapreduce.Job:  map 84% reduce 0%
18/01/05 12:04:40 INFO mapreduce.Job:  map 85% reduce 0%
18/01/05 12:04:41 INFO mapreduce.Job:  map 86% reduce 0%
18/01/05 12:04:42 INFO mapreduce.Job:  map 87% reduce 0%
18/01/05 12:04:45 INFO mapreduce.Job:  map 88% reduce 0%
18/01/05 12:04:50 INFO mapreduce.Job:  map 89% reduce 0%
18/01/05 12:04:51 INFO mapreduce.Job:  map 90% reduce 0%
18/01/05 12:04:52 INFO mapreduce.Job:  map 92% reduce 0%
18/01/05 12:04:55 INFO mapreduce.Job:  map 92% reduce 10%
18/01/05 12:04:56 INFO mapreduce.Job:  map 93% reduce 10%
18/01/05 12:04:57 INFO mapreduce.Job:  map 93% reduce 14%
18/01/05 12:04:58 INFO mapreduce.Job:  map 93% reduce 19%
18/01/05 12:04:59 INFO mapreduce.Job:  map 94% reduce 23%
18/01/05 12:05:00 INFO mapreduce.Job:  map 95% reduce 27%
18/01/05 12:05:01 INFO mapreduce.Job:  map 96% reduce 27%
18/01/05 12:05:02 INFO mapreduce.Job:  map 97% reduce 27%
18/01/05 12:05:03 INFO mapreduce.Job:  map 97% reduce 29%
18/01/05 12:05:04 INFO mapreduce.Job:  map 97% reduce 30%
18/01/05 12:05:05 INFO mapreduce.Job:  map 97% reduce 31%
18/01/05 12:05:06 INFO mapreduce.Job:  map 98% reduce 32%
18/01/05 12:05:07 INFO mapreduce.Job:  map 100% reduce 32%
18/01/05 12:05:09 INFO mapreduce.Job:  map 100% reduce 38%
18/01/05 12:05:10 INFO mapreduce.Job:  map 100% reduce 44%
18/01/05 12:05:11 INFO mapreduce.Job:  map 100% reduce 50%
18/01/05 12:05:12 INFO mapreduce.Job:  map 100% reduce 56%
18/01/05 12:05:13 INFO mapreduce.Job:  map 100% reduce 70%
18/01/05 12:05:15 INFO mapreduce.Job:  map 100% reduce 71%
18/01/05 12:05:16 INFO mapreduce.Job:  map 100% reduce 73%
18/01/05 12:05:17 INFO mapreduce.Job:  map 100% reduce 75%
18/01/05 12:05:18 INFO mapreduce.Job:  map 100% reduce 77%
18/01/05 12:05:19 INFO mapreduce.Job:  map 100% reduce 83%
18/01/05 12:05:21 INFO mapreduce.Job:  map 100% reduce 86%
18/01/05 12:05:22 INFO mapreduce.Job:  map 100% reduce 89%
18/01/05 12:05:23 INFO mapreduce.Job:  map 100% reduce 92%
18/01/05 12:05:24 INFO mapreduce.Job:  map 100% reduce 94%
18/01/05 12:05:26 INFO mapreduce.Job:  map 100% reduce 97%
18/01/05 12:05:27 INFO mapreduce.Job:  map 100% reduce 100%
18/01/05 12:05:28 INFO mapreduce.Job: Job job_1515171482176_0002 completed successfully
18/01/05 12:05:28 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2914502898
                FILE: Number of bytes written=5787390070
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=6553630396
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=630
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=204
                Launched reduce tasks=6
                Data-local map tasks=204
                Total time spent by all maps in occupied slots (ms)=1875409
                Total time spent by all reduces in occupied slots (ms)=279296
                Total time spent by all map tasks (ms)=1875409
                Total time spent by all reduce tasks (ms)=279296
                Total vcore-seconds taken by all map tasks=1875409
                Total vcore-seconds taken by all reduce tasks=279296
                Total megabyte-seconds taken by all map tasks=1920418816
                Total megabyte-seconds taken by all reduce tasks=285999104
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Map output bytes=6684672000
                Map output materialized bytes=2846121654
                Input split bytes=30396
                Combine input records=0
                Combine output records=0
                Reduce input groups=65536000
                Reduce shuffle bytes=2846121654
                Reduce input records=65536000
                Reduce output records=65536000
                Spilled Records=131072000
                Shuffled Maps =1224
                Failed Shuffles=0
                Merged Map outputs=1224
                GC time elapsed (ms)=29789
                CPU time spent (ms)=1027530
                Physical memory (bytes) snapshot=110553513984
                Virtual memory (bytes) snapshot=335120089088
                Total committed heap usage (bytes)=116938768384
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
18/01/05 12:05:28 INFO terasort.TeraSort: done

real    3m0.889s
user    0m8.273s
sys     0m0.377s
[ec2-user@ip-172-31-7-166 ~]$


```
