# MAVEN installation on EC2 instance
### Pre-requisites
1. EC2 instance with port access-SSH/TCP/22 and what ever services enabled
2. Need Java ( maven supported ) version
-------------------------------------------------------
### Install Apache MAVEN with package managers:
Debian = sudo apt install maven

Redhat = sudo yum/dnf install maven

### Install Apache MAVEN manually:

Download maven packages = https://downloads.apache.org/maven/ in /opt/maven as my installation directory

```
  # Creating maven directory under /opt
  mkdir /opt/maven
  cd /opt/maven
  # downloading maven version 3.8.8
  wget https://downloads.apache.org/maven/maven-3/3.8.8/source/apache-maven-3.8.8-src.tar.gz
  unzip /opt/maven/apache-maven-3.8.8-bin.zip
 ```
Setup M2_HOME and M2 paths in .bash_profile or .bashrc of user and add these to path variable
```sh
  vi ~/.bash_profile
  M2_HOME=/opt/maven/apache-maven-3.8.8
  M2=$M2_HOME/bin
  PAHT=<Existing_PATH>:$M2_HOME:$M2
```
#### Check point 
source ~/.bash_profile  # source
logoff and login to check maven version
Check maven version 
```sh
  mvn –version
```
So far you have completed installation of maven software
