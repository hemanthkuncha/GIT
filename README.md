#user data

-- used to run any commands/script in the initial stage of EC2 startup

1. It need shebang [ !#/bin/bash ]
2. It will more likely work after encoding in base64.
---------------------------------------------------------
####HTTPD installation script in normal & Base64 Encoded format for YUM - REDHAT based: 

```sh#!/bin/bash
sudo yum install -y git
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
sudo git clone https://github.com/Akiranred/ecomm.git /var/www/html
-----------------------------------------------------------------------
IyEvYmluL2Jhc2gKc3VkbyB5dW0gaW5zdGFsbCAteSBnaXQKc3VkbyB5dW0gaW5zdGFsbCAteSBodHRwZApzdWRvIHN5c3RlbWN0bCBzdGFydCBodHRwZApzdWRvIHN5c3RlbWN0bCBlbmFibGUgaHR0cGQKc3VkbyBnaXQgY2xvbmUgaHR0cHM6Ly9naXRodWIuY29tL0FraXJhbnJlZC9lY29tbS5naXQgL3Zhci93d3cvaHRtbA==
   ```
