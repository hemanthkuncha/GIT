HTTPD Apache Archive Distribution Directory link = https://archive.apache.org/dist/httpd/

HTTPD = Apache Hypertext Transfer Protocol (HTTP) server / HyperText Transfer Protocol Daemon

httpd is a software program that runs in the background and serves as a web server, handling client requests and delivering web content.

It listens for incoming network requests (usually from web browsers) and responds by sending back the requested web pages, images, or other resources. 

httpd operates using a client-server model, where clients (like web browsers) send requests to the server (httpd) and the server responds with the requested data. 

Open source

# HTTPD installation on EC2 instance
### Pre-requisites
1. EC2 instance with port access-SSH/TCP/22 and what ever services enabled - web/TCP/80-default http port
2. Need httpd ( * ) any version

### Install Apache HTTPD with package managers:
1.Debian = sudo apt-get/apt install apache2

1.Redhat = sudo yum/dnf install httpd

### Install Apache HTTPD manually:

Root Directory = /var/www/html

-----------------------------------

config file name = httpd.conf

if port changes needed or any other configuration

---------------------------------------

some OS need firewall rules allow


1. Download tomcat packages from https://archive.apache.org/dist/httpd/ onto /opt on EC2 instance
   > Note: Make sure you change `<version>` with the tomcat version which you download. 
   ```sh 
   # Create tomcat directory
   cd /opt
   wget https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.35/bin/apache-tomcat-8.5.35.tar.gz
   tar -xvzf /opt/apache-tomcat-<version>.tar.gz
   ```
1. give executing permissions to startup.sh and shutdown.sh which are under bin. 
   ```sh
   chmod +x /opt/apache-tomcat-<version>/bin/startup.sh 
   chmod +x /opt/apache-tomcat-<version>/bin/shutdown.sh
   ```
   > Note: you may get below error while starting tomcat incase if you dont install Java   
   `Neither the JAVA_HOME nor the JRE_HOME environment variable is defined At least one of these environment variable is needed to run this program`
1. create link files for tomcat startup.sh and shutdown.sh 
   ```sh
   ln -s /opt/apache-tomcat-<version>/bin/startup.sh /usr/local/bin/tomcatup
   ln -s /opt/apache-tomcat-<version>/bin/shutdown.sh /usr/local/bin/tomcatdown
   tomcatup
   ```
  #### Check point :
access tomcat application from browser on port 8080  
 - http://<Public_IP>:8080

  Using unique ports for each application is a best practice in an environment. But tomcat and Jenkins runs on ports number 8080. Hence lets change tomcat port number to 8090. Change port number in conf/server.xml file under tomcat home
   ```sh
 cd /opt/apache-tomcat-<version>/conf
# update port number in the "connecter port" field in server.xml
# restart tomcat after configuration update
tomcatdown
tomcatup
```
#### Check point :
Access tomcat application from browser on port 8090  
 - http://<Public_IP>:8090

1. now application is accessible on port 8090. but tomcat application doesnt allow to login from browser. changing a default parameter in context.xml does address this issue
   ```sh
   #search for context.xml
   find / -name context.xml
   ```
1. above command gives 3 context.xml files. comment (<!-- & -->) `Value ClassName` field on files which are under webapp directory. 
After that restart tomcat services to effect these changes. 
At the time of writing this lecture below 2 files are updated. 
   ```sh 
   /opt/tomcat/webapps/host-manager/META-INF/context.xml
   /opt/tomcat/webapps/manager/META-INF/context.xml
   
   # Restart tomcat services
   tomcatdown  
   tomcatup
   ```
1. Update users information in the tomcat-users.xml file
goto tomcat home directory and Add below users to conf/tomcat-users.xml file without any spaces infront of lines
   ```sh
	<role rolename="manager-gui"/>
   <role rolename="admin-gui"/>
	<role rolename="manager-script"/>
	<role rolename="manager-jmx"/>
	<role rolename="manager-status"/>
	<user username="admin" password="admin" roles="manager-gui, roles="admin-gui, manager-script, manager-jmx, manager-status"/>
	<user username="deployer" password="deployer" roles="manager-script"/>
	<user username="tomcat" password="tomcat" roles="manager-gui"/>
   ```
1. Restart serivce and try to login to tomcat application from the browser. This time it should be Successful
