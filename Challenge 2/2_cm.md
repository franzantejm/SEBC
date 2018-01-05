
List the command and output for ls /etc/yum.repos.d in

```

[ec2-user@ip-172-31-7-166 /]$ ls /etc/yum.repos.d
cloudera-manager.repo  mysql-community-source.repo  redhat-rhui-client-config.repo  rhui-load-balancers.conf
mysql-community.repo   redhat.repo                  redhat-rhui.repo


```



Use the scm_prepare_database.sh script to create the db.properties file
List the full command and its output in 2_cm.md


```


[ec2-user@ip-172-31-7-166 /]$ sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-14-139.us-west-2.compute.internal -utemp -ptemppwd --scm-host ip-172-31-7-166.us-west-2.compute.internal scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!




```
