Java Apache Archive Distribution Directory link = https://www.oracle.com/in/java/technologies/downloads/archive/

java -version 

-------------------

Java followed Legacy versioning untill 1.8=8

version| name

1=1.1,2=1.2,3=1.3-----,8=1.8

-----------------------------

9=9,10=10,11=11,-----25=25...

INSTALLATION:

Debian = sudo apt install ( java-8-openjdk-amd64  java-11-openjdk-amd64  java-17-openjdk-amd64 )

Redhat = sudo yum/dnf install (  java-8-openjdk-amd64  java-11-openjdk-amd64  java-17-openjdk-amd64 ) / java-1.8*

Set the JAVA_HOME Variable
Edit your .bash_profile or .bashrc
nano ~/.bash_profile

1.sudo update-alternatives --config java ( switching java version using command )

NOTE: in some cases using "alternatives --config java"  for redhat

====================================================

2.add java home path to $PATH ( switching java version using manually setting )

searching java installed path [ which java , whereis java]

searching java in complete filesystem [ find / -name "java"]

java binary = [/usr/lib/jvm/java-1.8.0-amazon-corretto.x86_64/jre/bin/java]

for java selction - use = [/usr/lib/jvm/java-1.8.0-amazon-corretto.x86_64]

-----------------------------------------------------------------------------------

{ JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export PATH=$JAVA_HOME/bin:$PATH  }

source ~/.bash_profile  # source

===================================================
