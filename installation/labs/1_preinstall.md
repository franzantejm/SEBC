
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

3
<br/>
<code> 
sudo /sbin/tune2fs -l /dev/xvdb
<code/>
<br/>

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
4.
<br/>
<code> 
sudo vim /boot/grub/menu.lst

<code/>

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

output
<br/>
cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]

<br/>


5.
<br/>
<code> 
sudo /sbin/ifconfig -a
<code/>
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


