 cloud provider:AWS
 
Instances:

ec2-34-223-215-67.us-west-2.compute.amazonaws.com
34.223.215.67

ec2-52-10-228-0.us-west-2.compute.amazonaws.com
52.10.228.0               

ec2-52-27-9-156.us-west-2.compute.amazonaws.com
52.27.9.156

ec2-52-43-201-168.us-west-2.compute.amazonaws.com
52.43.201.168




LINUX SUSE 11.3 SP3

ec2-user@172-31-12-96::~> sudo df
Filesystem     1K-blocks    Used Available Use% Mounted on
devtmpfs        16434620       8  16434612   1% /dev
tmpfs           16473236       0  16473236   0% /dev/shm
tmpfs           16473236   13628  16459608   1% /run
/dev/xvda1      30831592 1326676  28125496   5% /
tmpfs           16473236       0  16473236   0% /sys/fs/cgroup
tmpfs            3294648       0   3294648   0% /run/user/1000




 ec2-user@172-31-12-96::~> sudo useradd -u 2800 -m saturn
useradd: warning: the home directory already exists.
Not copying any file from skel directory into it.
Creating mailbox file: File exists


ec2-user@172-31-12-96::~> sudo useradd -u 2900 -m haley
ec2-user@172-31-12-96::~> sudo useradd -u 2900 -m saturn


ec2-user@ip-172-31-12-96:~> sudo groupadd comets
ec2-user@ip-172-31-12-96:~> sudo groupadd planets





ec2-user@172-31-12-96::~> sudo usermod -g comets haley
ec2-user@172-31-12-96::~> sudo usermod -g planets saturn



ec2-user@172-31-12-96::~> sudo cat /etc/passwd | tail -n2
saturn:x:2800:1001::/home/saturn:/bin/bash
haley:x:2900:1000::/home/haley:/bin/bash


ec2-user@ip-172-31-4-152:~> sudo cat /etc/group | tail -n2
comets:x:1000:
planets:x:1001:





