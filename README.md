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

## How to new line in md file
write (space,space)  
write  

## Installing java 7 on centos 7
REf: https://tecadmin.net/steps-to-install-java-on-centos-5-6-or-rhel-5-6/  
wget  "https://download.java.net/openjdk/jdk7u75/ri/openjdk-7u75-b13-linux-x64-18_dec_2014.tar.gz"  
tar xzf openjdk-7u75-b13-linux-x64-18_dec_2014.tar.gz   
cd /opt/java-se-7u75-ri/  
alternatives --install /usr/bin/java java /opt/java-se-7u75-ri/bin/java 2  
alternatives --config java  
alternatives --install /usr/bin/jar jar /opt/java-se-7u75-ri/bin/jar 2  
lternatives --install /usr/bin/javac javac /opt/java-se-7u75-ri/bin/javac 2  
alternatives --install /usr/bin/javac javac /opt/java-se-7u75-ri/bin/javac 2  
alternatives --set jar /opt/java-se-7u75-ri/bin/jar  
alternatives --set javac /opt/java-se-7u75-ri/bin/javac  
java -version  

## Opening the port 8080 and 8443 in centos 7

https://www.thegeekdiary.com/how-to-open-a-ports-in-centos-rhel-7/  
netstat -na |grep 8443  
lsof -i -P |grep http
lsof -i -P |grep https
iptables-save | grep 8443
iptables-save | grep 8080
vi /etc/services
firewall-cmd --zone=public --add-port=8080/tcp --permanent
firewall-cmd --zone=public --add-port=8443/tcp --permanent
firewall-cmd --reload
iptables-save | grep 8443
iptables-save | grep 8080
Try to connect to the service  
lsof -i -P |grep http
lsof -i -P |grep https
netstat -na |grep 8443
netstat -na |grep 8080


