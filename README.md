HTTPD Apache Archive Distribution Directory link = https://archive.apache.org/dist/httpd/

HTTPD = Apache Hypertext Transfer Protocol (HTTP) server / HyperText Transfer Protocol Daemon

httpd is a software program that runs in the background and serves as a web server, handling client requests and delivering web content.

It listens for incoming network requests (usually from web browsers) and responds by sending back the requested web pages, images, or other resources. 

httpd operates using a client-server model, where clients (like web browsers) send requests to the server (httpd) and the server responds with the requested data. 

Open source

# HTTPD installation on EC2 instance
### Pre-requisites
1. EC2 instance with port access-SSH/TCP/22 and what ever services enabled - web/TCP/80-default http port
### Install Apache HTTPD with package managers:
Debian = sudo apt-get/apt install apache2

Redhat = sudo yum/dnf install httpd

### Install Apache HTTPD manually:
pending

Root Directory = /var/www/html

-----------------------------------

config file name = httpd.conf/ports.conf

if port changes needed or any other configuration

---------------------------------------

some OS need firewall rules allow

--------------------------------------------

check with http://public ip : port
