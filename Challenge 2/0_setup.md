List the cloud provider
```

AWS Oregon

```

List your instances by IP address and DNS name


```

NODO 1 ec2-52-43-213-117.us-west-2.compute.amazonaws.com	172.31.44.234	ip-172-31-44-234.us-west-2.compute.internal
NODO 2 ec2-54-70-174-78.us-west-2.compute.amazonaws.com	172.31.35.208	ip-172-31-35-208.us-west-2.compute.internal
NODO 3 ec2-35-166-7-229.us-west-2.compute.amazonaws.com	172.31.40.133	ip-172-31-40-133.us-west-2.compute.internal
NODO 4 ec2-54-70-176-100.us-west-2.compute.amazonaws.com		172.31.11.93	ip-172-31-11-93.us-west-2.compute.internal


```


List the Linux release you are using

  ```
[ec2-user@ip-172-31-3-219 ~]$ sudo cat /proc/version
Linux version 3.10.0-327.36.3.el7.x86_64 (mockbuild@x86-037.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-4) (GCC) ) #1 SMP Thu Oct 20 04:56:07 EDT 2016


[ec2-user@ip-172-31-3-219 ~]$ sudo cat  /etc/redhat-release
Red Hat Enterprise Linux Server release 7.2 (Maipo)



```


List the file system capacity for the first node


  ```
[ec2-user@ip-172-31-3-219 ~]$ sudo df -hT
Filesystem     Type      Size  Used Avail Use% Mounted on
/dev/xvda2     xfs        30G  1.4G   29G   5% /
devtmpfs       devtmpfs   15G     0   15G   0% /dev
tmpfs          tmpfs      15G     0   15G   0% /dev/shm
tmpfs          tmpfs      15G   17M   15G   1% /run
tmpfs          tmpfs      15G     0   15G   0% /sys/fs/cgroup
/dev/xvdc      ext4       99G   61M   94G   1% /datadisk
/dev/xvdb      ext4       99G  108M   94G   1% /logdisk
tmpfs          tmpfs     3.0G     0  3.0G   0% /run/user/1000




```



List the command and output for yum repolist enabled

```
[ec2-user@ip-172-31-3-219 ~]$ yum repo list enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
No such command: repo. Please use /usr/bin/yum --help
[ec2-user@ip-172-31-3-219 ~]$


```



List the file system capacity for the first node


  ```
[ec2-user@ip-172-31-3-219 ~]$ sudo cat /etc/passwd | grep 'haley\|saturn'
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash


```


List the /etc/group entries for comets and planets

```

[ec2-user@ip-172-31-3-219 ~]$ sudo cat /etc/group | grep 'planets\|comets'
planets:x:2901:saturn
comets:x:2902:haley

```







