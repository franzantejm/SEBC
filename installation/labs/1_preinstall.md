# CM INSTALL LAB SYSTEM CONFIGURATION CHECK

1

sudo  /sbin/sysctl vm.swappiness=1


Output
vm.swappiness=1


2



cat /etc/fstab




Output

devpts  /dev/pts          devpts  mode=0620,gid=5 0 0
proc    /proc             proc    defaults        0 0
sysfs   /sys              sysfs   noauto          0 0
debugfs /sys/kernel/debug debugfs noauto          0 0
tmpfs   /run              tmpfs   noauto          0 0
/dev/hda1 / ext3 defaults 1  1
/dev/hda1 / ext3 defaults 1 1
UUID=d8370529-62da-4755-8ac2-a253f9d864de /data01 ext4    defaults        0       2
UUID=1ba217b2-c29d-4c48-9256-d61e09d85bb6 /data02 ext4    defaults        0       2
<br/>

3
<code>
 
sudo /sbin/tune2fs -l /dev/xvdb

<code/>

output
<br/>
tune2fs 1.41.9 (22-Aug-2009)
Filesystem volume name:   <none>
Last mounted on:          <not available>
Filesystem UUID:          d8370529-62da-4755-8ac2-a253f9d864de
Filesystem magic number:  0xEF53
Filesystem revision #:    1 (dynamic)
Filesystem features:      has_journal ext_attr resize_inode dir_index filetype extent flex_bg sparse_super large_file huge_file uninit_bg dir_nlink extra_isize
Filesystem flags:         signed_directory_hash
Default mount options:    (none)
Filesystem state:         clean
Errors behavior:          Continue
Filesystem OS type:       Linux
Inode count:              6553600
Block count:              26214400
Reserved block count:     1310720
Free blocks:              25755051
Free inodes:              6553589
First block:              0
Block size:               4096
Fragment size:            4096
Reserved GDT blocks:      1017
Blocks per group:         32768
Fragments per group:      32768
Inodes per group:         8192
Inode blocks per group:   512
Flex block group size:    16
Filesystem created:       Mon Oct  2 13:47:44 2017
Last mount time:          n/a
Last write time:          Mon Oct  2 17:09:20 2017
Mount count:              0
Maximum mount count:      33
Last checked:             Mon Oct  2 13:47:44 2017
Check interval:           15552000 (6 months)
Next check after:         Sat Mar 31 13:47:44 2018
Lifetime writes:          1733 MB
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
First inode:              11
Inode size:               256
Required extra isize:     28
Desired extra isize:      28
Journal inode:            8
Default directory hash:   half_md4
Directory Hash Seed:      b8cd1b77-0369-49a3-9aa5-79a6af6bc59a
Journal backup:           inode blocks
<br/>
4
<br/>

sudo vim /boot/grub/menu.lst

<br/>

output
<br/>
timeout 1
title SLES11-SP4-EC2-HVM
 kernel (hd0,0)/boot/vmlinuz-3.0.101-104-default root=/dev/hda1 disk=/dev/hda  vga=0x314   console=tty0 console=ttyS0,115200n8 multipath=off NON_PERSISTENT_DEVICE_NAMES=1 quiet showopts  transparent_hugepage = never
 initrd (hd0,0)/boot/initrd-3.0.101-104-default
title Failsafe_--_SLES11-SP4-EC2-HVM
 kernel (hd0,0)/boot/vmlinuz-3.0.101-104-default root=/dev/hda1 disk=/dev/hda  vga=0x314   console=tty0 console=ttyS0,115200n8 multipath=off NON_PERSISTENT_DEVICE_NAMES=1 ide=nodma apm=off noresume edd=off powersaved=off nohz=off highres=off processsor.max+cstate=1 nomodeset x11failsafe quiet showopts
 initrd (hd0,0)/boot/initrd-3.0.101-104-default

<br/>

sudo /sbin/ifconfig -a
<br/>
output

<br/>
eth0      Link encap:Ethernet  HWaddr 0A:FA:AD:61:89:2A
          inet addr:172.31.23.127  Bcast:172.31.31.255  Mask:255.255.240.0
          UP BROADCAST RUNNING MULTICAST  MTU:9000  Metric:1
          RX packets:1097 errors:0 dropped:4 overruns:0 frame:0
          TX packets:925 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:89457 (87.3 Kb)  TX bytes:98522 (96.2 Kb)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
          RX packets:2 errors:0 dropped:0 overruns:0 frame:0
          TX packets:2 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          
      <br/>
      
      
 6
  <br/>
  

 nslookup www.google.com
<br/>
 
 output 
 <br/>
 
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   www.google.com
Address: 216.58.202.132

<br/>

CODE

getent hosts

Output
127.0.0.1       localhost
54.232.112.38   smt-ec2.susecloud.net smt-ec2




7.
ps -ef | grep nscd
root      2985     1  0 17:52 ?        00:00:00 /usr/sbin/nscd
ec2-user  3888  3444  0 18:27 pts/0    00:00:00 grep nscd


sudo /etc/init.d/ntp start

ps -ef | grep ntpd
ntp       3944     1  0 18:32 ?        00:00:00 /usr/sbin/ntpd -p /var/run/ntp/ntpd.pid -g -u ntp:ntp -c /etc/ntp.conf
ntp       3948  3944  0 18:32 ?        00:00:00 ntpd: asynchronous dns resolver
ec2-user  3953  3444  0 18:32 pts/0    00:00:00 grep ntpd






#MYSQL INSTALL LAB




ec2-user@ip-172-31-23-127:~> sudo /etc/init.d/mysql start
Starting service MySQL

#CM PATH B

1
sudo rpm -Uvh jdk-8u141-linux-x64.rpm


Preparing...                ########################################### [100%]
   1:jdk1.8.0_141           ########################################### [100%]
Unpacking JAR files...
        tools.jar...
        plugin.jar...
        javaws.jar...
        deploy.jar...
        rt.jar...
        jsse.jar...
        charsets.jar...
        localedata.jar...
/usr/sbin/alternatives not available, skip registering alternatives for java...
2
installed by defect

3

sql> create database hue  DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

mysql> DROP DATABASE hue;
Query OK, 0 rows affected (0.00 sec)

mysql> create database amon  DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

mysql> grant all on damon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
Query OK, 0 rows affected (0.00 sec)

mysql> create database rman  DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

mysql> grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
Query OK, 0 rows affected (0.00 sec)

mysql> create database metastore  DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

mysql> grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
Query OK, 0 rows affected (0.00 sec)

mysql> create database sentry  DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

mysql> grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
Query OK, 0 rows affected (0.00 sec)


4

mysql -u root -p

grant all on *.* to 'temp'@'%' identified by 'temp' with grant option;


sudo netstat -ano | grep 7180



5 INSTALL CM

udo rpm -Uvh cloudera-manager-agent-5.10.0-1.cm5100.p0.85.sles11.x86_64.rpm
warning: cloudera-manager-agent-5.10.0-1.cm5100.p0.85.sles11.x86_64.rpm: Header V4 DSA signature: NOKEY, key ID e8f86acd
error: Failed dependencies:
        python-psycopg2 is needed by cloudera-manager-agent-5.10.0-1.cm5100.p0.85.sles11.x86_64
ec2-user@ip-172-31-23-127:/> sudo rpm -Uvh /home/ec2-user/python-psycopg2-2.6-2.1.x86_64.rpm
warning: /home/ec2-user/python-psycopg2-2.6-2.1.x86_64.rpm: Header V3 DSA signature: NOKEY, key ID edf0d733
Preparing...                ########################################### [100%]
   1:python-psycopg2        ########################################### [100%]
ec2-user@ip-172-31-23-127:/> sudo rpm -Uvh cloudera-manager-agent-5.10.0-1.cm5100.p0.85.sles11.x86_64.rpm
warning: cloudera-manager-agent-5.10.0-1.cm5100.p0.85.sles11.x86_64.rpm: Header V4 DSA signature: NOKEY, key ID e8f86acd
Preparing...                ########################################### [100%]
   1:cloudera-manager-agent ########################################### [100%]
ec2-user@ip-172-31-23-127:/>


sudo /etc/init.d/cloudera-scm-server start
Starting cloudera-scm-server:                                                                                       done

ec2-user@ip-172-31-23-127:~> sudo /etc/init.d/cloudera-scm-server status
Checking for service cloudera-scm-server                                                                            running



