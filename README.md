# debugging
## How to install Indic TTS on machine without training 

https://github.com/AI4Bharat/Indic-TTS

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

## How to install maven on centos

https://linuxize.com/post/how-to-install-apache-maven-on-centos-7/  

java should be installed and java home to be known
wget http://apachemirror.wuchna.com/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz -P /tmp 
tar xf /tmp/apache-maven-3.6.1-bin.tar.gz -C /opt  
ls /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.201.b09-2.el7_6.x86_64  
tar xf /tmp/apache-maven-3.6.1-bin.tar.gz -C /opt  
ln -s /opt/apache-maven-3.6.1 /opt/maven  
echo $JAVA_HOME  
java -version  
which java  
ls -l /usr/bin/java  
ls -l /etc/alternatives/java  
vi /etc/profile.d/maven.sh  
chmod +x /etc/profile.d/maven.sh  
source /etc/profile.d/maven.sh  

## How to enable wifi in dell laptop of latitude 3400
990  cd /lib/firmware/ath10k/QCA9377/hw1.0/  
  991  ls  
  992  cat notice_ath10k_firmware-6.txt   
  993   ls  
  994  clear  
  995    
  996  rm -rf firmware-6.bin  
  997  sudo rm -rf firmware-6.bin   
  998  sudo rm notice_ath10k_firmware-6.txt  
  999  ls  
 1000  reboot  


