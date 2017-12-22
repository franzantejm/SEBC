A command and output that shows the hostname of your database server

```

mysql> select @@hostname;
+--------------------------------------------+
| @@hostname                                 |
+--------------------------------------------+
| ip-172-31-3-219.us-west-2.compute.internal |
+--------------------------------------------+
1 row in set (0.00 sec)


```
A command and output that reports the database server version

```
mysql> SELECT @@VERSION;
+-----------+
| @@VERSION |
+-----------+
| 5.5.58    |
+-----------+
1 row in set (0.00 sec)



```

A command and output that lists all the databases in the server


```

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)



```
