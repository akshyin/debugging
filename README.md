# debugging
## How to uninstall java from linux
https://novicestuffs.wordpress.com/2017/04/25/how-to-uninstall-java-from-linux/
## How to Install PostgreSQL Relational Databases on CentOS 7
https://www.linode.com/docs/databases/postgresql/how-to-install-postgresql-relational-databases-on-centos-7/
https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7.6-x86_64/
Steps:
 rpm -q centos-release \s
 wget https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7.6-x86_64/pgdg-centos10-10-2.noarch.rpm
 yum install pgdg-centos10-10-2.noarch.rpm  
 yum install pgdg-centos10-10-2.noarch.rpm epel-release.noarch  
 yum update 
 yum install postgresql10-server.x86_64 postgresql10-contrib.x86_64   
 /usr/pgsql-10/bin/postgresql-10-setup initdb 
 systemctl start postgresql-10.service  
 systemctl enable postgresql-10.service  
 
 ## How to use remote desktop on CentOS 7
at centos 
yum -y install epel-release
yum -y install x11vnc
x11vnc -storepasswd
x11vnc --reopen --forever -rfbauth ~/.vncpasswd &
at ubuntu for vnc
install vinagre

caution: 1. use password less than 8 character. move file at server from /root/.vnc/passwd to /root/.vncpasswd
