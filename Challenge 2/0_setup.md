List the cloud provider
```

AWS Oregon

```

List your instances by IP address and DNS name


```

NODO_1	ec2-34-214-244-14.us-west-2.compute.amazonaws.com		172.31.14.139	ip-172-31-14-139.us-west-2.compute.internal
NODO_2	ec2-52-42-254-48.us-west-2.compute.amazonaws.com		172.31.7.166	ip-172-31-7-166.us-west-2.compute.internal
NODO_3	ec2-54-69-61-65.us-west-2.compute.amazonaws.com		172.31.8.180	ip-172-31-8-180.us-west-2.compute.internal
NODO_4	ec2-34-215-143-27.us-west-2.compute.amazonaws.com		172.31.3.219	ip-172-31-3-219.us-west-2.compute.internal



```


List the Linux release you are using

  ```
[ec2-user@ip-172-31-14-139 ~]$ sudo cat /proc/version
Linux version 3.10.0-327.36.3.el7.x86_64 (mockbuild@x86-037.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-4) (GCC) ) #1 SMP Thu Oct 20 04:56:07 EDT 2016



[ec2-user@ip-172-31-14-139 ~]$ sudo cat  /etc/redhat-release
Red Hat Enterprise Linux Server release 7.2 (Maipo)




```


List the file system capacity for the first node


  ```
[ec2-user@ip-172-31-14-139 ~]$ sudo df -hT
Filesystem     Type      Size  Used Avail Use% Mounted on
/dev/xvda2     xfs        30G  1.3G   29G   5% /
devtmpfs       devtmpfs   15G     0   15G   0% /dev
tmpfs          tmpfs      15G     0   15G   0% /dev/shm
tmpfs          tmpfs      15G   17M   15G   1% /run
tmpfs          tmpfs      15G     0   15G   0% /sys/fs/cgroup
/dev/xvdb      ext4       99G   61M   94G   1% /logdisk
/dev/xvdc      ext4       99G   61M   94G   1% /datadisk
tmpfs          tmpfs     3.0G     0  3.0G   0% /run/user/1000





```



List the command and output for yum repolist enabled

```
[ec2-user@ip-172-31-14-139 ~]$ yum repo list enabled
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



```



List the /etc/passwd entries for saturn and haley


  ```
[ec2-user@ip-172-31-14-139 ~]$ sudo cat /etc/passwd | grep 'haley\|saturn'
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash


```


List the /etc/group entries for comets and planets

```

[ec2-user@ip-172-31-14-139 ~]$ sudo cat /etc/group | grep 'planets\|comets'
planets:x:2901:saturn
comets:x:2902:haley

```







