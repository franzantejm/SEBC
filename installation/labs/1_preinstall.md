
#############################################
5 
SETEAR swapp para mejorar manejo de memoria
####################################
sudo /sbin/sysctl vm.swappiness=1


#########6

setear transparente_huge=1

sudo vim /boot/grub/menu.lst

transparent_hugepage=1



#########7

start  NTP service

sudo /etc/init.d/ntp start
sudo vim /etc/ntp.conf
#NTP Argentina
server 0.ar.pool.ntp.org
server 0.south-america.pool.ntp.org
server 3.south-america.pool.ntp.org

#########
8    ESTABLECER REPO Mysql e instalar
#########


sudo wget https://dev.mysql.com/get/mysql57-community-release-sles11-8.noarch.rpm

sudo rpm -Uvh mysql57-community-release-sles11-8.noarch.rpm


-----------------------------------------------------------------------
ec2-user@ip-172-31-5-174:/home/paquetes> sudo rpm -Uvh mysql57-community-release-sles11-8.noarch.rpm
warning: mysql57-community-release-sles11-8.noarch.rpm: Header V3 DSA signature: NOKEY, key ID 5072e1f5
Preparing...                ########################################### [100%]
   1:mysql57-community-relea########################################### [100%]
ec2-user@ip-172-31-5-174:/home/paquetes>
-----------------------------------------------------------------------




sudo /etc/init.d/mysql start





-----------------------------------------------------------------------
PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
To do so, start the server, then issue the following commands:

/usr/bin/mysqladmin -u root password 'new-password'
/usr/bin/mysqladmin -u root -h ip-172-31-11-254 password 'new-password'

Alternatively you can run:
/usr/bin/mysql_secure_installation

which will also give you the option of removing the test
databases and anonymous user created by default.  This is
strongly recommended for production servers.

See the manual for more instructions.

You can start the MySQL daemon with:
rcmysql start

You can test the MySQL daemon with mysql-test package

Please report any problems at http://bugs.mysql.com/

Starting service MySQL                                                                                    done
----------------------------------------------------------------------------------------------------------------------------------------------




###########################
9 MYSQL SECURE INSTALATION
###########################


sudo /usr/bin/mysql_secure_installation

----------------------------------

y default, MySQL comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...



All done!  If you've completed all of the above steps, your MySQL
installation should now be secure.

Thanks for using MySQL!



----------------------------------



###########################
10 Instalar JDK  !"""""""""""""""""" sudo zypper install jdk1.7.0_67-cloudera
###########################

sudo wget 
http://download.oracle.com/otn/java/jdk/8u141-b15/336fa29ff2bb4ef291e347e091f7f4a7/jdk-8u141-linux-x64.rpm

sudo rpm -Uvh jdk-8u144-linux-x64.rpm

sudo wget http://archive.cloudera.com/cm5/sles/11/x86_64/cm/5.11.0/RPMS/x86_64/oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm
sudo rpm - i oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm
----------------------------------



###########################
11 CM
###########################

#11.1 bajar paquetes

sudo wget http://archive.cloudera.com/cm5/sles/11/x86_64/cm/5.11.0/RPMS/x86_64/cloudera-manager-agent-5.11.0-1.cm5110.p0.101.sles11.x86_64.rpm
sudo wget http://archive.cloudera.com/cm5/sles/11/x86_64/cm/5.11.0/RPMS/x86_64/cloudera-manager-daemons-5.11.0-1.cm5110.p0.101.sles11.x86_64.rpm
sudo wget http://archive.cloudera.com/cm5/sles/11/x86_64/cm/5.11.0/RPMS/x86_64/cloudera-manager-server-5.11.0-1.cm5110.p0.101.sles11.x86_64.rpm




###########################
12 INSTALAR BASES
###########################

create database amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';

create database rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';

create database metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';

create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';

create database hue DEFAULT CHARACTER SET utf8;
grant all on hue.* TO 'hue'@'%' IDENTIFIED BY 'sentry_password';
grant all on hue.* TO 'hue'@'localhost' IDENTIFIED BY 'sentry_password';



Oozie
create database oozie DEFAULT CHARACTER SET utf8;
grant all on oozie.* TO 'oozie'@'localhost' IDENTIFIED BY 'oozie_password';




###########################
13 instalar paquetes CM
###########################
sudo rpm -Uvh cloudera-manager-agent-5.11.0-1.cm5110.p0.101.sles11.x86_64.rpm

sudo rpm -Uvh  
###########################
Dependencias para CM
###########################
sudo wget install postgresql
sudo zypper install  python-mysql

sudo wget ftp://ftp.pbone.net/mirror/ftp5.gwdg.de/pub/opensuse/repositories/devel:/languages:/python/SLE_11_SP4/x86_64/python-psycopg2-2.6-1.14.x86_64.rpm




sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h localhost -utemp -ptemp --scm-host localhost scm scm scm




sudo rm -rf scm_prepare_node.*


