# 怎样在CentOS/RHEL 7/6/5 和 Fedora上安装Java8 #
经过漫长的等待，Java SE8开发工具包终于可供下载。2014年3月18日 JDK 8与许多增强功能全面上市。您可以在[这里](http://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html "这里")了解JDK8的增强功能。

 ![](http://tecadmin.net/wp-content/uploads/2013/12/linux-with-java.png)

这篇文章将会帮助你安装Java8（JDK 8u45）或者升级你的系统。仔细读取下面的Linux命令来安装Java。如果你是Ubuntu或LinuxMint，请阅读[这篇文章](http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa/ "这篇文章")。
下载最新的Java
从[官网](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html "官网")下载最新的Java SE 8或者用以下命令下载。
For 64Bit

    # cd /opt/
    # wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-linux-x64.tar.gz"
    
    # tar xzf jdk-8u45-linux-x64.tar.gz
For 32Bit

    # cd /opt/
    # wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-linux-i586.tar.gz"
    
    # tar xzf jdk-8u45-linux-i586.tar.gz

注意：如果以上wget命令无法运行，请看视频用终端下载Java源码。
用命令行安装Java 
解压文件之后用命令行安装。命令行在chkconfig包里面。	

    # cd /opt/jdk1.8.0_45/
    # alternatives --install /usr/bin/java java /opt/jdk1.8.0_45/bin/java 2
    # alternatives --config java


到这里的时候，Java8已经成功安装到你的系统中，我们推荐用命令行将javac和jar命令添加到path里面。

    # alternatives --install /usr/bin/jar jar /opt/jdk1.8.0_45/bin/jar 2
    # alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_45/bin/javac 2
    # alternatives --set jar /opt/jdk1.8.0_45/bin/jar
    # alternatives --set javac /opt/jdk1.8.0_45/bin/javac 
检测安装好的Java版本号
用以下命令检测安装好的Java版本号。

    root@tecadmin ~# java -version
    
    
    java version "1.8.0_45"
    Java(TM) SE Runtime Environment (build 1.8.0_45-b14)
    Java HotSpot(TM) 64-Bit Server VM (build 25.45-b02, mixed mode)
    
配置环境变量
大多是Java基础程序需要环境变量支持才能工作，用以下命令来设置Java的环境变量。

    •	设置JAVA_HOME 变量
    # export JAVA_HOME=/opt/jdk1.8.0_45
    •	设置JRE_HOME 变量
    # export JRE_HOME=/opt/jdk1.8.0_45/jre
    •	设置PATH 变量
    # export PATH=$PATH:/opt/jdk1.8.0_45/bin:/opt/jdk1.8.0_45/jre/bin

你也可以更改/etc/enviroment文件来达到目的。

原文：[http://tecadmin.net/install-java-8-on-centos-rhel-and-fedora/](http://tecadmin.net/install-java-8-on-centos-rhel-and-fedora/ "http://tecadmin.net/install-java-8-on-centos-rhel-and-fedora/")