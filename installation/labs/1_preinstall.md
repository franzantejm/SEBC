
For all nodes:
<br/>


1-
<br/>

<code>
 sudo  /sbin/sysctl vm.swappiness=1
<code/>
<br/>
Output
vm.swappiness=1
<br/>

2-
<br/>

<code> 
cat /etc/fstab
<code/>
<br/>


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
