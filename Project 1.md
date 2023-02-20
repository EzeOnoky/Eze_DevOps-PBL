# WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
Everything you will be doing as a DevOps engineer is around software, websites, applications etc. And, there are different stack of technologies that make different solutions possible. These stack of technologies are regarded as WEB STACKS. Examples of Web Stacks include LAMP, LEMP, MEAN, and MERN stacks. As you proceed in your journey, you will be required to understand and implement all of these technology stacks.

define s = Character(_("Sylvie"), color="#c8ffc8")
define m = Character(_("Me"), color="#c8c8ff")

## What is a Technology stack?
A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. Below are the list of the Technology Stack

LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)
LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
MEAN (MongoDB, ExpressJS, AngularJS, NodeJS

## STEP 1 — INSTALLING APACHE AND UPDATING THE FIREWALL
What exactly is Apache? Apache HTTP Server is the most widely used web server software. Developed and maintained by Apache Software Foundation, Apache is an open source software available for free. It runs on 67% of all webservers in the world. It is fast, reliable, and secure. Websites and other applications can run on other web server software as well. Such as Nginx, Microsoft’s IIS, etc

The Apache web server is among the most popular web servers in the world, this makes it a great default choice for hosting a website.

Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\EZEPC> ssh -i "EzeUbuntu.pem" ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com
Warning: Identity file EzeUbuntu.pem not accessible: No such file or directory.
The authenticity of host 'ec2-34-232-44-62.compute-1.amazonaws.com (34.232.44.62)' can't be established.
ECDSA key fingerprint is SHA256:iI7fBN3JQiEAzZjIcOa3NudegCQl47z/Ip4wZ9Ik9Jg.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: Y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added 'ec2-34-232-44-62.compute-1.amazonaws.com,34.232.44.62' (ECDSA) to the list of known hosts.
ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com: Permission denied (publickey).
PS C:\Users\EZEPC> ssh -i "EzeUbuntu.pem" ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com
Warning: Identity file EzeUbuntu.pem not accessible: No such file or directory.
ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com: Permission denied (publickey).
PS C:\Users\EZEPC> ssh -i "EzeUbuntu.pem" ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com
Warning: Identity file EzeUbuntu.pem not accessible: No such file or directory.
ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com: Permission denied (publickey).
PS C:\Users\EZEPC> cd Desktop
PS C:\Users\EZEPC\Desktop> cd DevOps
PS C:\Users\EZEPC\Desktop\DevOps> ssh -i "EzeUbuntu.pem" ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-1028-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue Feb 14 02:54:43 UTC 2023

  System load:  0.025390625       Processes:             98
  Usage of /:   30.2% of 7.57GB   Users logged in:       0
  Memory usage: 56%               IPv4 address for eth0: 172.31.11.176
  Swap usage:   0%

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

1 update can be applied immediately.
1 of these updates is a standard security update.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Mon Feb 13 14:47:42 2023 from 105.112.182.126
ubuntu@ip-172-31-11-176:~$ sudo mkdir /var/www/projectlamp
mkdir: cannot create directory ‘/var/www/projectlamp’: File exists
ubuntu@ip-172-31-11-176:~$ sudo chown -R $USER:$USER /var/www/projectlamp
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ ls
ubuntu@ip-172-31-11-176:~$ sudo ls /etc/apache2/sites-available
000-default.conf  default-ssl.conf  projectlamp.conf
ubuntu@ip-172-31-11-176:~$ sudo a2ensite projectlamp
Site projectlamp already enabled
ubuntu@ip-172-31-11-176:~$ sudo a2dissite 000-default
Site 000-default already disabled
ubuntu@ip-172-31-11-176:~$ sudo apache2ctl configtest
apache2: Syntax error on line 225 of /etc/apache2/apache2.conf: Syntax error on line 8 of /etc/apache2/sites-enabled/projectlamp.conf: </VirtlHost without matching <VirtlHost section
Action 'configtest' failed.
The Apache error log may have more information.
ubuntu@ip-172-31-11-176:~$ sudo systemctl reload apache2
apache2.service is not active, cannot reload.
ubuntu@ip-172-31-11-176:~$ sudo ls /etc/apache2/sites-available
000-default.conf  default-ssl.conf  projectlamp.conf
ubuntu@ip-172-31-11-176:~$ client_loop: send disconnect: Connection reset
PS C:\Users\EZEPC\Desktop\DevOps> ssh -i "EzeUbuntu.pem" ubuntu@ec2-34-232-44-62.compute-1.amazonaws.com
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-1028-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue Feb 14 03:42:49 UTC 2023

  System load:  0.0               Processes:             100
  Usage of /:   30.2% of 7.57GB   Users logged in:       1
  Memory usage: 56%               IPv4 address for eth0: 172.31.11.176
  Swap usage:   0%

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

1 update can be applied immediately.
1 of these updates is a standard security update.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Tue Feb 14 02:54:44 2023 from 105.112.182.126
ubuntu@ip-172-31-11-176:~$
ubuntu@ip-172-31-11-176:~$
ubuntu@ip-172-31-11-176:~$ sudo mkdir /var/www/projectlamp
mkdir: cannot create directory ‘/var/www/projectlamp’: File exists
ubuntu@ip-172-31-11-176:~$ sudo chown -R $USER:$USER /var/www/projectlamp
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ sudo ls /etc/apache2/sites-available
000-default.conf  default-ssl.conf  projectlamp.conf
ubuntu@ip-172-31-11-176:~$ 000-default.conf  default-ssl.conf  projectlamp.conf
000-default.conf: command not found
ubuntu@ip-172-31-11-176:~$ sudo a2ensite projectlamp
Site projectlamp already enabled
ubuntu@ip-172-31-11-176:~$ sudo a2dissite 000-default
Site 000-default already disabled
ubuntu@ip-172-31-11-176:~$ sudo apache2ctl configtest
apache2: Syntax error on line 225 of /etc/apache2/apache2.conf: Syntax error on line 8 of /etc/apache2/sites-enabled/projectlamp.conf: </VirtlHost without matching <VirtlHost section
Action 'configtest' failed.
The Apache error log may have more information.
ubuntu@ip-172-31-11-176:~$ man sudo
ubuntu@ip-172-31-11-176:~$ sudo rm
rm: missing operand
Try 'rm --help' for more information.
ubuntu@ip-172-31-11-176:~$ sudo edit
ubuntu@ip-172-31-11-176:~$ Connection to ec2-34-232-44-62.compute-1.amazonaws.com closed by remote host.
Connection to ec2-34-232-44-62.compute-1.amazonaws.com closed.
PS C:\Users\EZEPC\Desktop\DevOps> ssh -i "EzeUbuntu.pem" ubuntu@ec2-44-200-245-82.compute-1.amazonaws.com
The authenticity of host 'ec2-44-200-245-82.compute-1.amazonaws.com (44.200.245.82)' can't be established.
ECDSA key fingerprint is SHA256:iI7fBN3JQiEAzZjIcOa3NudegCQl47z/Ip4wZ9Ik9Jg.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ec2-44-200-245-82.compute-1.amazonaws.com,44.200.245.82' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-1028-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue Feb 14 04:09:13 UTC 2023

  System load:  0.81787109375     Processes:             104
  Usage of /:   30.2% of 7.57GB   Users logged in:       0
  Memory usage: 56%               IPv4 address for eth0: 172.31.11.176
  Swap usage:   0%

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

1 update can be applied immediately.
1 of these updates is a standard security update.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Tue Feb 14 03:42:50 2023 from 105.112.182.126
ubuntu@ip-172-31-11-176:~$ /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ sudo mkdir /var/www/projectlamp
mkdir: cannot create directory ‘/var/www/projectlamp’: File exists
ubuntu@ip-172-31-11-176:~$ sudo chown -R $USER:$USER /var/www/projectlamp
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ cat /etc/apache2/sites-available/projectlamp.conf
i<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtlHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>>
ubuntu@ip-172-31-11-176:~$ true > /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ true > /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ cd /etc/apache2/sites-available/projectlamp.conf
-bash: cd: /etc/apache2/sites-available/projectlamp.conf: Not a directory
ubuntu@ip-172-31-11-176:~$ cd etc/apache2/sites-available/projectlamp.conf
-bash: cd: etc/apache2/sites-available/projectlamp.conf: No such file or directory
ubuntu@ip-172-31-11-176:~$ sudo true > /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ sudo /etc/apache2/sites-available/projectlamp.conf
sudo: /etc/apache2/sites-available/projectlamp.conf: command not found
ubuntu@ip-172-31-11-176:~$ true > /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ sudo !!
sudo true > /etc/apache2/sites-available/projectlamp.conf
-bash: /etc/apache2/sites-available/projectlamp.conf: Permission denied
ubuntu@ip-172-31-11-176:~$ sudo vi /etc/apache2/sites-available/projectlamp.conf
ubuntu@ip-172-31-11-176:~$ sudo apache2ctl configtest
Syntax OK
ubuntu@ip-172-31-11-176:~$ sudo systemctl reload apache2
apache2.service is not active, cannot reload.
ubuntu@ip-172-31-11-176:~$ sudo systemctl status apache2
× apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: failed (Result: exit-code) since Tue 2023-02-14 04:08:56 UTC; 41min ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 429 ExecStart=/usr/sbin/apachectl start (code=exited, status=1/FAILURE)
        CPU: 33ms

Feb 14 04:08:55 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:08:56 ip-172-31-11-176 apachectl[445]: apache2: Syntax error on line 225 of /etc/apache2/apache2.conf: Syntax error on line 8 of /etc/apa>
Feb 14 04:08:56 ip-172-31-11-176 apachectl[429]: Action 'start' failed.
Feb 14 04:08:56 ip-172-31-11-176 apachectl[429]: The Apache error log may have more information.
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: apache2.service: Control process exited, code=exited, status=1/FAILURE
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: apache2.service: Failed with result 'exit-code'.
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: Failed to start The Apache HTTP Server.
Feb 14 04:49:53 ip-172-31-11-176 systemd[1]: apache2.service: Unit cannot be reloaded because it is inactive.
...skipping...
× apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: failed (Result: exit-code) since Tue 2023-02-14 04:08:56 UTC; 41min ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 429 ExecStart=/usr/sbin/apachectl start (code=exited, status=1/FAILURE)
        CPU: 33ms

Feb 14 04:08:55 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:08:56 ip-172-31-11-176 apachectl[445]: apache2: Syntax error on line 225 of /etc/apache2/apache2.conf: Syntax error on line 8 of /etc/apa>
Feb 14 04:08:56 ip-172-31-11-176 apachectl[429]: Action 'start' failed.
Feb 14 04:08:56 ip-172-31-11-176 apachectl[429]: The Apache error log may have more information.
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: apache2.service: Control process exited, code=exited, status=1/FAILURE
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: apache2.service: Failed with result 'exit-code'.
Feb 14 04:08:56 ip-172-31-11-176 systemd[1]: Failed to start The Apache HTTP Server.
Feb 14 04:49:53 ip-172-31-11-176 systemd[1]: apache2.service: Unit cannot be reloaded because it is inactive.
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
ubuntu@ip-172-31-11-176:~$ sudo systemctl start apache2
ubuntu@ip-172-31-11-176:~$ sudo systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-02-14 04:51:05 UTC; 19s ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 1096 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)
   Main PID: 1100 (apache2)
      Tasks: 6 (limit: 1143)
     Memory: 12.3M
        CPU: 45ms
     CGroup: /system.slice/apache2.service
             ├─1100 /usr/sbin/apache2 -k start
             ├─1101 /usr/sbin/apache2 -k start
             ├─1102 /usr/sbin/apache2 -k start
             ├─1103 /usr/sbin/apache2 -k start
             ├─1104 /usr/sbin/apache2 -k start
             └─1105 /usr/sbin/apache2 -k start

Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Started The Apache HTTP Server.
ubuntu@ip-172-31-11-176:~$ sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
ubuntu@ip-172-31-11-176:~$
ubuntu@ip-172-31-11-176:~$
ubuntu@ip-172-31-11-176:~$ sudo vim /etc/apache2/mods-enabled/dir.conf
ubuntu@ip-172-31-11-176:~$ sudo systemctl reload apache2
Job for apache2.service failed.
See "systemctl status apache2.service" and "journalctl -xeu apache2.service" for details.
ubuntu@ip-172-31-11-176:~$ sudo systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-02-14 04:51:05 UTC; 23min ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 1096 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)
    Process: 1204 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=1/FAILURE)
   Main PID: 1100 (apache2)
      Tasks: 7 (limit: 1143)
     Memory: 13.2M
        CPU: 127ms
     CGroup: /system.slice/apache2.service
             ├─1100 /usr/sbin/apache2 -k start
             ├─1101 /usr/sbin/apache2 -k start
             ├─1102 /usr/sbin/apache2 -k start
             ├─1103 /usr/sbin/apache2 -k start
             ├─1104 /usr/sbin/apache2 -k start
             ├─1105 /usr/sbin/apache2 -k start
             └─1118 /usr/sbin/apache2 -k start

Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Started The Apache HTTP Server.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reloading The Apache HTTP Server...
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1207]: apache2: Syntax error on line 147 of /etc/apache2/apache2.conf: Syntax error on line 6 of /etc/ap>
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: Action 'graceful' failed.
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: The Apache error log may have more information.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: apache2.service: Control process exited, code=exited, status=1/FAILURE
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reload failed for The Apache HTTP Server.
...skipping...
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-02-14 04:51:05 UTC; 23min ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 1096 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)
    Process: 1204 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=1/FAILURE)
   Main PID: 1100 (apache2)
      Tasks: 7 (limit: 1143)
     Memory: 13.2M
        CPU: 127ms
     CGroup: /system.slice/apache2.service
             ├─1100 /usr/sbin/apache2 -k start
             ├─1101 /usr/sbin/apache2 -k start
             ├─1102 /usr/sbin/apache2 -k start
             ├─1103 /usr/sbin/apache2 -k start
             ├─1104 /usr/sbin/apache2 -k start
             ├─1105 /usr/sbin/apache2 -k start
             └─1118 /usr/sbin/apache2 -k start

Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Started The Apache HTTP Server.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reloading The Apache HTTP Server...
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1207]: apache2: Syntax error on line 147 of /etc/apache2/apache2.conf: Syntax error on line 6 of /etc/ap>
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: Action 'graceful' failed.
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: The Apache error log may have more information.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: apache2.service: Control process exited, code=exited, status=1/FAILURE
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reload failed for The Apache HTTP Server.
~
~
~
~
~
~
~
~
~
~
~
~
~
~
ubuntu@ip-172-31-11-176:~$ sudo systemctl start apache2
ubuntu@ip-172-31-11-176:~$ sudo systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-02-14 04:51:05 UTC; 24min ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 1096 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)
    Process: 1204 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=1/FAILURE)
   Main PID: 1100 (apache2)
      Tasks: 7 (limit: 1143)
     Memory: 13.2M
        CPU: 128ms
     CGroup: /system.slice/apache2.service
             ├─1100 /usr/sbin/apache2 -k start
             ├─1101 /usr/sbin/apache2 -k start
             ├─1102 /usr/sbin/apache2 -k start
             ├─1103 /usr/sbin/apache2 -k start
             ├─1104 /usr/sbin/apache2 -k start
             ├─1105 /usr/sbin/apache2 -k start
             └─1118 /usr/sbin/apache2 -k start

Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Starting The Apache HTTP Server...
Feb 14 04:51:05 ip-172-31-11-176 systemd[1]: Started The Apache HTTP Server.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reloading The Apache HTTP Server...
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1207]: apache2: Syntax error on line 147 of /etc/apache2/apache2.conf: Syntax error on line 6 of /etc/ap>
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: Action 'graceful' failed.
Feb 14 05:13:33 ip-172-31-11-176 apachectl[1204]: The Apache error log may have more information.
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: apache2.service: Control process exited, code=exited, status=1/FAILURE
Feb 14 05:13:33 ip-172-31-11-176 systemd[1]: Reload failed for The Apache HTTP Server.
ubuntu@ip-172-31-11-176:~$ sudo systemctl start apache2
ubuntu@ip-172-31-11-176:~$ sudo systemctl reload apache2
Job for apache2.service failed.
See "systemctl status apache2.service" and "journalctl -xeu apache2.service" for details.
ubuntu@ip-172-31-11-176:~$ cat /etc/apache2/mods-enabled/dir.conf
<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule><IfModule mod_dir.c>
        DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
</IfModule>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
ubuntu@ip-172-31-11-176:~$ rm dir.conf
rm: cannot remove 'dir.conf': No such file or directory
ubuntu@ip-172-31-11-176:~$ rmdir /etc/apache2/mods-enabled/dir.conf
rmdir: failed to remove '/etc/apache2/mods-enabled/dir.conf': Permission denied
ubuntu@ip-172-31-11-176:~$ man rm
ubuntu@ip-172-31-11-176:~$ rmdir -r /etc/apache2/mods-enabled/dir.conf
rmdir: invalid option -- 'r'
Try 'rmdir --help' for more information.
ubuntu@ip-172-31-11-176:~$ rm -r /etc/apache2/mods-enabled/dir.conf
rm: cannot remove '/etc/apache2/mods-enabled/dir.conf': Permission denied
ubuntu@ip-172-31-11-176:~$ man sudo !!
man sudo rm -r /etc/apache2/mods-enabled/dir.conf
--Man-- next: rm(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

No manual entry for -rNo manual entry for -r
--Man-- next: dir.conf [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

ubuntu@ip-172-31-11-176:~$ sudo apt-get purge php*
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'php-composer-metadata-minifier' for glob 'php*'
Note, selecting 'php-symfony-config' for glob 'php*'
Note, selecting 'php8.1-enchant' for glob 'php*'
Note, selecting 'php-phpseclib3' for glob 'php*'
Note, selecting 'phpunit-php-code-coverage' for glob 'php*'
Note, selecting 'php-nyholm-psr7' for glob 'php*'
Note, selecting 'phpqrcode' for glob 'php*'
Note, selecting 'php-mapscript' for glob 'php*'
Note, selecting 'php-net-ipv6' for glob 'php*'
Note, selecting 'php-http-webdav-server' for glob 'php*'
Note, selecting 'php-apcu' for glob 'php*'
Note, selecting 'php-phpseclib-file-x509' for glob 'php*'
Note, selecting 'php-mdb2-driver-ibase' for glob 'php*'
Note, selecting 'php-dragonmantank-cron-expression' for glob 'php*'
Note, selecting 'php-barnabywalters-mf-cleaner' for glob 'php*'
Note, selecting 'php-alcaeus-mongo-php-adapter' for glob 'php*'
Note, selecting 'php-mdb2-driver-fbsql' for glob 'php*'
Note, selecting 'php-symfony-message-bird-notifier' for glob 'php*'
Note, selecting 'php-net-publicsuffix' for glob 'php*'
Note, selecting 'php-symfony-zulip-notifier' for glob 'php*'
Note, selecting 'php8.1-simplexml' for glob 'php*'
Note, selecting 'php7.2-common' for glob 'php*'
Note, selecting 'php8.1-mysqlnd' for glob 'php*'
Note, selecting 'php8.1-pspell' for glob 'php*'
Note, selecting 'php-symfony-infobip-notifier' for glob 'php*'
Note, selecting 'php8.1-raphf' for glob 'php*'
Note, selecting 'php-geos' for glob 'php*'
Note, selecting 'php-phar-io-version' for glob 'php*'
Note, selecting 'php-symfony-service-contracts' for glob 'php*'
Note, selecting 'php-dbase' for glob 'php*'
Note, selecting 'php-net-ldap2' for glob 'php*'
Note, selecting 'php-net-ldap3' for glob 'php*'
Note, selecting 'php-zmq-all-dev' for glob 'php*'
Note, selecting 'php-enchant' for glob 'php*'
Note, selecting 'php-psr-link' for glob 'php*'
Note, selecting 'php-net-dime' for glob 'php*'
Note, selecting 'php-redis' for glob 'php*'
Note, selecting 'php-psr-http-message' for glob 'php*'
Note, selecting 'php-rhumsaa-uuid' for glob 'php*'
Note, selecting 'php8.1-interbase' for glob 'php*'
Note, selecting 'php-http-httplug' for glob 'php*'
Note, selecting 'php-pdo-dblib' for glob 'php*'
Note, selecting 'php-xmlrpc' for glob 'php*'
Note, selecting 'php-mdb2-driver-oci8' for glob 'php*'
Note, selecting 'php-finder-facade-doc' for glob 'php*'
Note, selecting 'php8.1-bcmath' for glob 'php*'
Note, selecting 'php-uuid-all-dev' for glob 'php*'
Note, selecting 'php-symfony-beanstalkd-messenger' for glob 'php*'
Note, selecting 'php-mdb2-driver-odbc' for glob 'php*'
Note, selecting 'php5.6-json' for glob 'php*'
Note, selecting 'php-symfony-smsc-notifier' for glob 'php*'
Note, selecting 'php-phpmyadmin-motranslator' for glob 'php*'
Note, selecting 'php-text-figlet' for glob 'php*'
Note, selecting 'php-net-dns2' for glob 'php*'
Note, selecting 'php-doctrine-data-fixtures' for glob 'php*'
Note, selecting 'php-elasticsearch' for glob 'php*'
Note, selecting 'php-gettext-languages' for glob 'php*'
Note, selecting 'php-symfony-sendgrid-mailer' for glob 'php*'
Note, selecting 'php-monolog' for glob 'php*'
Note, selecting 'php-mysqlnd' for glob 'php*'
Note, selecting 'php-math-biginteger' for glob 'php*'
Note, selecting 'php-phpdocumentor-reflection-common' for glob 'php*'
Note, selecting 'php-solr-all-dev' for glob 'php*'
Note, selecting 'php-email-validator' for glob 'php*'
Note, selecting 'php8.1-ctype' for glob 'php*'
Note, selecting 'php-container-interop' for glob 'php*'
Note, selecting 'php8.1-pgsql' for glob 'php*'
Note, selecting 'php-ocramius-proxy-manager' for glob 'php*'
Note, selecting 'php-symfony-discord-notifier' for glob 'php*'
Note, selecting 'php-symfony-service-implementation' for glob 'php*'
Note, selecting 'php-phpseclib-system-ssh-agent' for glob 'php*'
Note, selecting 'php8.1-gnupg' for glob 'php*'
Note, selecting 'php7.0-thrift' for glob 'php*'
Note, selecting 'php-klogger' for glob 'php*'
Note, selecting 'php-moontoast-math' for glob 'php*'
Note, selecting 'phpunit-cli-parser' for glob 'php*'
Note, selecting 'php-cordoval-hamcrest-php' for glob 'php*'
Note, selecting 'php-ramsey-uuid-doctrine' for glob 'php*'
Note, selecting 'php-ramsey-uuid' for glob 'php*'
Note, selecting 'php-getallheaders' for glob 'php*'
Note, selecting 'php-doctrine-inflector' for glob 'php*'
Note, selecting 'php-deepcopy' for glob 'php*'
Note, selecting 'php-symfony-gitter-notifier' for glob 'php*'
Note, selecting 'php-psr-cache' for glob 'php*'
Note, selecting 'php-symfony-browser-kit' for glob 'php*'
Note, selecting 'php-xmlwriter' for glob 'php*'
Note, selecting 'php-htmlawed' for glob 'php*'
Note, selecting 'php8.1-iconv' for glob 'php*'
Note, selecting 'php-guzzlehttp-guzzle' for glob 'php*'
Note, selecting 'php-symfony-framework-bundle' for glob 'php*'
Note, selecting 'php-mail' for glob 'php*'
Note, selecting 'php8.1-sass' for glob 'php*'
Note, selecting 'php-zend-stdlib' for glob 'php*'
Note, selecting 'php-mapi' for glob 'php*'
Note, selecting 'php-symfony-sinch-notifier' for glob 'php*'
Note, selecting 'php-symfony-telegram-notifier' for glob 'php*'
Note, selecting 'php-league-flysystem' for glob 'php*'
Note, selecting 'php8.1-msgpack' for glob 'php*'
Note, selecting 'php-psr-http-factory' for glob 'php*'
Note, selecting 'php-guzzlehttp-promises' for glob 'php*'
Note, selecting 'php-async-aws-core' for glob 'php*'
Note, selecting 'php8.1-gmagick' for glob 'php*'
Note, selecting 'php-mdb2' for glob 'php*'
Note, selecting 'php-suhosin' for glob 'php*'
Note, selecting 'php-easyrdf' for glob 'php*'
Note, selecting 'php7.2-sodium' for glob 'php*'
Note, selecting 'php8.1-pdo-mysql' for glob 'php*'
Note, selecting 'php-phpseclib-file-ansi' for glob 'php*'
Note, selecting 'php-symfony-dotenv' for glob 'php*'
Note, selecting 'php-symfony-expo-notifier' for glob 'php*'
Note, selecting 'php5' for glob 'php*'
Note, selecting 'phpwebcounter-extra' for glob 'php*'
Note, selecting 'phpunit-code-unit' for glob 'php*'
Note, selecting 'php-symfony-mailer' for glob 'php*'
Note, selecting 'php-http-interop-http-factory-tests' for glob 'php*'
Note, selecting 'php-symfony-security-http' for glob 'php*'
Note, selecting 'php-twig-html-extra' for glob 'php*'
Note, selecting 'php-text-languagedetect' for glob 'php*'
Note, selecting 'php-friendsofphp-proxy-manager-lts' for glob 'php*'
Note, selecting 'php-symfony-redis-messenger' for glob 'php*'
Note, selecting 'php-symfony-process' for glob 'php*'
Note, selecting 'php-cache-lite' for glob 'php*'
Note, selecting 'php-phpseclib-file-asn1' for glob 'php*'
Note, selecting 'php-malkusch-lock' for glob 'php*'
Note, selecting 'php-league-commonmark' for glob 'php*'
Note, selecting 'php-wikidiff2' for glob 'php*'
Note, selecting 'php-msgpack' for glob 'php*'
Note, selecting 'php-symfony-amazon-sns-notifier' for glob 'php*'
Note, selecting 'php-mongodb-all-dev' for glob 'php*'
Note, selecting 'php' for glob 'php*'
Note, selecting 'php-symfony-polyfill-intl-normalizer' for glob 'php*'
Note, selecting 'php-phpdbg' for glob 'php*'
Note, selecting 'php-symfony-light-sms-notifier' for glob 'php*'
Note, selecting 'php-gmagick' for glob 'php*'
Note, selecting 'php-twig-cssinliner-extra' for glob 'php*'
Note, selecting 'php-pubsubhubbub-publisher' for glob 'php*'
Note, selecting 'php-symfony-deprecation-contracts' for glob 'php*'
Note, selecting 'php-symfony-dependency-injection' for glob 'php*'
Note, selecting 'php-symfony-translation' for glob 'php*'
Note, selecting 'phpunit-git' for glob 'php*'
Note, selecting 'php-pecl-http' for glob 'php*'
Note, selecting 'php-symfony-polyfill-xml' for glob 'php*'
Note, selecting 'php-symfony-semaphore' for glob 'php*'
Note, selecting 'php-phpseclib-net-sftp' for glob 'php*'
Note, selecting 'php-calendar' for glob 'php*'
Note, selecting 'php-cache-tag-interop' for glob 'php*'
Note, selecting 'php8.1-snmp' for glob 'php*'
Note, selecting 'php-mysqli' for glob 'php*'
Note, selecting 'php8.1-soap' for glob 'php*'
Note, selecting 'php-symfony-form' for glob 'php*'
Note, selecting 'php-mock' for glob 'php*'
Note, selecting 'php8.1-solr' for glob 'php*'
Note, selecting 'php-srmklive-flysystem-dropbox-v2' for glob 'php*'
Note, selecting 'php-symfony-fake-sms-notifier' for glob 'php*'
Note, selecting 'php-tokenizer' for glob 'php*'
Note, selecting 'php-net-whois' for glob 'php*'
Note, selecting 'php-doctrine-instantiator' for glob 'php*'
Note, selecting 'php-twig-intl-extra' for glob 'php*'
Note, selecting 'php-symfony-templating' for glob 'php*'
Note, selecting 'php-net-sieve' for glob 'php*'
Note, selecting 'php-net-url2' for glob 'php*'
Note, selecting 'php-symfony-security-bundle' for glob 'php*'
Note, selecting 'php8.1-pdo-sqlite' for glob 'php*'
Note, selecting 'php-league-flysystem-ziparchive' for glob 'php*'
Note, selecting 'php-doctrine-cache' for glob 'php*'
Note, selecting 'php-symfony-security-core' for glob 'php*'
Note, selecting 'php-proxy-manager' for glob 'php*'
Note, selecting 'php8.1-http' for glob 'php*'
Note, selecting 'php-symfony-polyfill-ctype' for glob 'php*'
Note, selecting 'php-mailparse-all-dev' for glob 'php*'
Note, selecting 'php-xdebug-all-dev' for glob 'php*'
Note, selecting 'php8.1-yaml' for glob 'php*'
Note, selecting 'php-fig-link-util' for glob 'php*'
Note, selecting 'php-finder-facade' for glob 'php*'
Note, selecting 'php8.1-ssh2' for glob 'php*'
Note, selecting 'php-sass' for glob 'php*'
Note, selecting 'php-mockery-doc' for glob 'php*'
Note, selecting 'php-league-flysystem-webdav' for glob 'php*'
Note, selecting 'php-symfony-oh-my-smtp-mailer' for glob 'php*'
Note, selecting 'php-pdo-firebird' for glob 'php*'
Note, selecting 'php-composer-xdebug-handler' for glob 'php*'
Note, selecting 'php-symfony-notifier' for glob 'php*'
Note, selecting 'php-symfony-ldap' for glob 'php*'
Note, selecting 'php-text-password' for glob 'php*'
Note, selecting 'php-directory-scanner' for glob 'php*'
Note, selecting 'php-phpmyadmin-sql-parser' for glob 'php*'
Note, selecting 'php-symfony-security-csrf' for glob 'php*'
Note, selecting 'php-php-http-client-implementation' for glob 'php*'
Note, selecting 'php-zeta-base' for glob 'php*'
Note, selecting 'php-psr-container' for glob 'php*'
Note, selecting 'php-symfony-polyfill-iconv' for glob 'php*'
Note, selecting 'php-psr-log-implementation' for glob 'php*'
Note, selecting 'php-symfony-smsapi-notifier' for glob 'php*'
Note, selecting 'php8.0-common' for glob 'php*'
Note, selecting 'php-stevenmaguire-oauth2-microsoft' for glob 'php*'
Note, selecting 'php-ssh2-all-dev' for glob 'php*'
Note, selecting 'php-zendframework-zend-eventmanager' for glob 'php*'
Note, selecting 'php-symfony-ovh-cloud-notifier' for glob 'php*'
Note, selecting 'php-symfony-http-client-contracts' for glob 'php*'
Note, selecting 'php-amqp-all-dev' for glob 'php*'
Note, selecting 'php-mdb2-driver-pgsql' for glob 'php*'
Note, selecting 'php-symfony-error-handler' for glob 'php*'
Note, selecting 'php-dasprid-enum' for glob 'php*'
Note, selecting 'php-phpseclib-net-ssh1' for glob 'php*'
Note, selecting 'php-phpseclib-net-ssh2' for glob 'php*'
Note, selecting 'phpunit-version' for glob 'php*'
Note, selecting 'php-symfony-lokalise-translation-provider' for glob 'php*'
Note, selecting 'php-spatie-flysystem-dropbox' for glob 'php*'
Note, selecting 'php-db' for glob 'php*'
Note, selecting 'php-league-html-to-markdown' for glob 'php*'
Note, selecting 'php-ds' for glob 'php*'
Note, selecting 'php-symfony-var-dumper' for glob 'php*'
Note, selecting 'php-gd' for glob 'php*'
Note, selecting 'php-ps' for glob 'php*'
Note, selecting 'php-symfony-twilio-notifier' for glob 'php*'
Note, selecting 'php-smbclient-all-dev' for glob 'php*'
Note, selecting 'php-symfony-doctrine-bridge' for glob 'php*'
Note, selecting 'php-common' for glob 'php*'
Note, selecting 'php-net-ftp' for glob 'php*'
Note, selecting 'php-libsodium' for glob 'php*'
Note, selecting 'php-twig-cache-extra' for glob 'php*'
Note, selecting 'php-mikey179-vfsstream' for glob 'php*'
Note, selecting 'php-symfony-linked-in-notifier' for glob 'php*'
Note, selecting 'php8.1-opcache' for glob 'php*'
Note, selecting 'php8.1-smbclient' for glob 'php*'
Note, selecting 'php-nrk-predis' for glob 'php*'
Note, selecting 'php-zeta-console-tools' for glob 'php*'
Note, selecting 'php-doctrine-dbal' for glob 'php*'
Note, selecting 'php-random-compat' for glob 'php*'
Note, selecting 'php-sybase' for glob 'php*'
Note, selecting 'php-symfony-twig-bridge' for glob 'php*'
Note, selecting 'php-psr-simple-cache' for glob 'php*'
Note, selecting 'php-laminas-eventmanager' for glob 'php*'
Note, selecting 'phpunit-object-enumerator' for glob 'php*'
Note, selecting 'php8.1-imagick' for glob 'php*'
Note, selecting 'php-snmp' for glob 'php*'
Note, selecting 'php8.1-mysql' for glob 'php*'
Note, selecting 'php-symfony-lock' for glob 'php*'
Note, selecting 'php-soap' for glob 'php*'
Note, selecting 'php-compat' for glob 'php*'
Note, selecting 'php-solr' for glob 'php*'
Note, selecting 'php-league-flysystem-cached-adapter' for glob 'php*'
Note, selecting 'php8.1-mailparse' for glob 'php*'
Note, selecting 'php-symfony-twig-bundle' for glob 'php*'
Note, selecting 'php-psr-log' for glob 'php*'
Note, selecting 'php-json-schema' for glob 'php*'
Note, selecting 'php8.1-curl' for glob 'php*'
Note, selecting 'php-image-text' for glob 'php*'
Note, selecting 'php-symfony-cache-contracts' for glob 'php*'
Note, selecting 'php-league-mime-type-detection' for glob 'php*'
Note, selecting 'php-league-flysystem-aws-s3-v2' for glob 'php*'
Note, selecting 'php-league-flysystem-aws-s3-v3' for glob 'php*'
Note, selecting 'php-http' for glob 'php*'
Note, selecting 'php-yaml' for glob 'php*'
Note, selecting 'php-uploadprogress-all-dev' for glob 'php*'
Note, selecting 'php-symfony-amazon-mailer' for glob 'php*'
Note, selecting 'phpunit-diff' for glob 'php*'
Note, selecting 'php-ssh2' for glob 'php*'
Note, selecting 'php-symfony-cache' for glob 'php*'
Note, selecting 'php-xml-rpc2' for glob 'php*'
Note, selecting 'php-http-promise' for glob 'php*'
Note, selecting 'php-symfony-cache-implementation' for glob 'php*'
Note, selecting 'php8.1' for glob 'php*'
Note, selecting 'php-vimeo-psalm' for glob 'php*'
Note, selecting 'php-oauth' for glob 'php*'
Note, selecting 'php-httpful' for glob 'php*'
Note, selecting 'php-mythtv' for glob 'php*'
Note, selecting 'php-console-table' for glob 'php*'
Note, selecting 'phpunit-type' for glob 'php*'
Note, selecting 'php-opcache' for glob 'php*'
Note, selecting 'php-libsmbclient' for glob 'php*'
Note, selecting 'php-validate' for glob 'php*'
Note, selecting 'php-imagick' for glob 'php*'
Note, selecting 'php-symfony-amqp-messenger' for glob 'php*'
Note, selecting 'php8.1-shmop' for glob 'php*'
Note, selecting 'php-phpstan-phpdoc-parser' for glob 'php*'
Note, selecting 'php-dompdf' for glob 'php*'
Note, selecting 'php-doctrine-lexer' for glob 'php*'
Note, selecting 'php8.1-tidy' for glob 'php*'
Note, selecting 'php-paragonie-random-lib' for glob 'php*'
Note, selecting 'php-zendframework-zend-stdlib' for glob 'php*'
Note, selecting 'php-symfony-options-resolver' for glob 'php*'
Note, selecting 'php-mdb2-driver-mssql' for glob 'php*'
Note, selecting 'php-mdb2-driver-sqlite' for glob 'php*'
Note, selecting 'php8.1-imap' for glob 'php*'
Note, selecting 'php-uploadprogress' for glob 'php*'
Note, selecting 'php7.3-common' for glob 'php*'
Note, selecting 'php-mcrypt' for glob 'php*'
Note, selecting 'php-net-url' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-twofish' for glob 'php*'
Note, selecting 'php8.1-intl' for glob 'php*'
Note, selecting 'php-ml-json-ld' for glob 'php*'
Note, selecting 'php-fdomdocument' for glob 'php*'
Note, selecting 'php7.4-fpm' for glob 'php*'
Note, selecting 'php-fileinfo' for glob 'php*'
Note, selecting 'php-bjeavons-zxcvbn-php' for glob 'php*'
Note, selecting 'php8.1-calendar' for glob 'php*'
Note, selecting 'php-twig-i18n-extension' for glob 'php*'
Note, selecting 'php-symfony-var-exporter' for glob 'php*'
Note, selecting 'php-symfony-serializer' for glob 'php*'
Note, selecting 'php-doctrine-annotations' for glob 'php*'
Note, selecting 'php-symfony-polyfill-php72' for glob 'php*'
Note, selecting 'php-symfony-polyfill-php73' for glob 'php*'
Note, selecting 'php-symfony-polyfill-php74' for glob 'php*'
Note, selecting 'php-pdepend' for glob 'php*'
Note, selecting 'php-symfony-polyfill-php80' for glob 'php*'
Note, selecting 'php-symfony-polyfill-php81' for glob 'php*'
Note, selecting 'php-apcu-all-dev' for glob 'php*'
Note, selecting 'phpunit-global-state' for glob 'php*'
Note, selecting 'php-console' for glob 'php*'
Note, selecting 'php-symfony-http-kernel' for glob 'php*'
Note, selecting 'php-symfony-mailgun-mailer' for glob 'php*'
Note, selecting 'php-symfony-web-profiler-bundle' for glob 'php*'
Note, selecting 'php-raphf' for glob 'php*'
Note, selecting 'php-imagick-all-dev' for glob 'php*'
Note, selecting 'php-doctrine-event-manager' for glob 'php*'
Note, selecting 'php7.0-common' for glob 'php*'
Note, selecting 'php-psr-cache-implementation' for glob 'php*'
Note, selecting 'php-pdo-pgsql' for glob 'php*'
Note, selecting 'php-symfony-property-access' for glob 'php*'
Note, selecting 'php-parser' for glob 'php*'
Note, selecting 'php8.1-odbc' for glob 'php*'
Note, selecting 'php-curl' for glob 'php*'
Note, selecting 'php-league-flysystem-eventable-filesystem' for glob 'php*'
Note, selecting 'php-arthurhoaro-web-thumbnailer' for glob 'php*'
Note, selecting 'php-getid3' for glob 'php*'
Note, selecting 'php-pclzip' for glob 'php*'
Note, selecting 'php-mdb2-driver-sqlsrv' for glob 'php*'
Note, selecting 'php-yaml-all-dev' for glob 'php*'
Note, selecting 'php-readline' for glob 'php*'
Note, selecting 'php-xdebug' for glob 'php*'
Note, selecting 'php-cache-integration-tests' for glob 'php*'
Note, selecting 'php-http-request2' for glob 'php*'
Note, selecting 'php-sabre-dav' for glob 'php*'
Note, selecting 'php-services-json' for glob 'php*'
Note, selecting 'php-async-aws-s3' for glob 'php*'
Note, selecting 'php-psr-link-implementation' for glob 'php*'
Note, selecting 'php-text-captcha' for glob 'php*'
Note, selecting 'php-amqplib' for glob 'php*'
Note, selecting 'php-igbinary' for glob 'php*'
Note, selecting 'php-phpseclib-math-biginteger' for glob 'php*'
Note, selecting 'php-ctype' for glob 'php*'
Note, selecting 'php-doctrine-couchdb' for glob 'php*'
Note, selecting 'php-igbinary-all-dev' for glob 'php*'
Note, selecting 'php-symfony-mime' for glob 'php*'
Note, selecting 'php-guzzlehttp-psr7' for glob 'php*'
Note, selecting 'php-tidy' for glob 'php*'
Note, selecting 'php-pgsql' for glob 'php*'
Note, selecting 'php-gnupg' for glob 'php*'
Note, selecting 'phpunit-object-reflector' for glob 'php*'
Note, selecting 'php-mdb2-driver-mysql' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-base' for glob 'php*'
Note, selecting 'php-imap' for glob 'php*'
Note, selecting 'phpunit-comparator' for glob 'php*'
Note, selecting 'php-symfony-translation-contracts' for glob 'php*'
Note, selecting 'php-symfony-microsoft-teams-notifier' for glob 'php*'
Note, selecting 'php-icinga' for glob 'php*'
Note, selecting 'phpunit-code-unit-reverse-lookup' for glob 'php*'
Note, selecting 'php-intl' for glob 'php*'
Note, selecting 'php-kodova-hamcrest-php' for glob 'php*'
Note, selecting 'php-http-psr7-integration-tests' for glob 'php*'
Note, selecting 'php-iconv' for glob 'php*'
Note, selecting 'phpunit-lines-of-code' for glob 'php*'
Note, selecting 'phpunit-resource-operations' for glob 'php*'
Note, selecting 'php-psr-simple-cache-implementation' for glob 'php*'
Note, selecting 'php-symfony-event-dispatcher-contracts' for glob 'php*'
Note, selecting 'phpunit-environment' for glob 'php*'
Note, selecting 'php-date' for glob 'php*'
Note, selecting 'php-graylog2-gelf-php' for glob 'php*'
Note, selecting 'php-nikic-fast-route' for glob 'php*'
Note, selecting 'php8.1-mysqli' for glob 'php*'
Note, selecting 'php-symfony-phpunit-bridge' for glob 'php*'
Note, selecting 'php-predis' for glob 'php*'
Note, selecting 'php-symfony-security-guard' for glob 'php*'
Note, selecting 'php8.1-memcache' for glob 'php*'
Note, selecting 'php-phpseclib' for glob 'php*'
Note, selecting 'php-simplexml' for glob 'php*'
Note, selecting 'php-composer-ca-bundle' for glob 'php*'
Note, selecting 'php-twig-markdown-extra' for glob 'php*'
Note, selecting 'php-console-color2' for glob 'php*'
Note, selecting 'php-symfony-routing' for glob 'php*'
Note, selecting 'php8.1-mbstring' for glob 'php*'
Note, selecting 'php-odbc' for glob 'php*'
Note, selecting 'php-msgpack-all-dev' for glob 'php*'
Note, selecting 'phpmyadmin' for glob 'php*'
Note, selecting 'php-gnupg-all-dev' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-aes' for glob 'php*'
Note, selecting 'php-xml-serializer' for glob 'php*'
Note, selecting 'php-symfony-vonage-notifier' for glob 'php*'
Note, selecting 'php-symfony-contracts' for glob 'php*'
Note, selecting 'php-symfony-mobyt-notifier' for glob 'php*'
Note, selecting 'php-symfony-message-media-notifier' for glob 'php*'
Note, selecting 'php-hamcrest' for glob 'php*'
Note, selecting 'php-depend' for glob 'php*'
Note, selecting 'php8.1-memcached' for glob 'php*'
Note, selecting 'phpab' for glob 'php*'
Note, selecting 'php-psr-event-dispatcher' for glob 'php*'
Note, selecting 'phpmd' for glob 'php*'
Note, selecting 'php-symfony-google-chat-notifier' for glob 'php*'
Note, selecting 'php-smbclient' for glob 'php*'
Note, selecting 'php-symfony-security-acl' for glob 'php*'
Note, selecting 'php7.2-thrift' for glob 'php*'
Note, selecting 'php-interbase' for glob 'php*'
Note, selecting 'php-twig' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-des' for glob 'php*'
Note, selecting 'php-symfony-sms77-notifier' for glob 'php*'
Note, selecting 'php-symfony-http-client' for glob 'php*'
Note, selecting 'php-symfony-polyfill-intl-messageformatter' for glob 'php*'
Note, selecting 'php5-ldap' for glob 'php*'
Note, selecting 'php-react-promise' for glob 'php*'
Note, selecting 'php-memcache' for glob 'php*'
Note, selecting 'php-mailparse' for glob 'php*'
Note, selecting 'php-oauth-all-dev' for glob 'php*'
Note, selecting 'php-rollbar' for glob 'php*'
Note, selecting 'php-pspell' for glob 'php*'
Note, selecting 'phpphylotree' for glob 'php*'
Note, selecting 'php-dapphp-radius' for glob 'php*'
Note, selecting 'php-symfony-slack-notifier' for glob 'php*'
Note, selecting 'php-patchwork-utf8' for glob 'php*'
Note, selecting 'php-composer-semver' for glob 'php*'
Note, selecting 'php-mbstring' for glob 'php*'
Note, selecting 'php8.1-fileinfo' for glob 'php*'
Note, selecting 'php-phpstan' for glob 'php*'
Note, selecting 'php-apc' for glob 'php*'
Note, selecting 'php-symfony-monolog-bridge' for glob 'php*'
Note, selecting 'php-mail-mime' for glob 'php*'
Note, selecting 'php-ast' for glob 'php*'
Note, selecting 'php-xajax' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-hash' for glob 'php*'
Note, selecting 'php-uopz-all-dev' for glob 'php*'
Note, selecting 'php-mariadb-mysql-kbs' for glob 'php*'
Note, selecting 'php-bz2' for glob 'php*'
Note, selecting 'php-symfony-console' for glob 'php*'
Note, selecting 'php-cas' for glob 'php*'
Note, selecting 'php-cgi' for glob 'php*'
Note, selecting 'php-cli' for glob 'php*'
Note, selecting 'php8.1-posix' for glob 'php*'
Note, selecting 'php-cpd' for glob 'php*'
Note, selecting 'php-codesniffer' for glob 'php*'
Note, selecting 'phpunit-recursion-context' for glob 'php*'
Note, selecting 'php-dba' for glob 'php*'
Note, selecting 'php-dev' for glob 'php*'
Note, selecting 'php-symfony-runtime' for glob 'php*'
Note, selecting 'php-structures-graph' for glob 'php*'
Note, selecting 'php-dom' for glob 'php*'
Note, selecting 'php8.1-uopz' for glob 'php*'
Note, selecting 'php-doctrine-orm' for glob 'php*'
Note, selecting 'php8.1-common' for glob 'php*'
Note, selecting 'php-htmlpurifier' for glob 'php*'
Note, selecting 'php-symfony-iqsms-notifier' for glob 'php*'
Note, selecting 'php-ffi' for glob 'php*'
Note, selecting 'php-symfony-dom-crawler' for glob 'php*'
Note, selecting 'php8.1-xmlrpc' for glob 'php*'
Note, selecting 'php-fpm' for glob 'php*'
Note, selecting 'phpcpd' for glob 'php*'
Note, selecting 'php-ftp' for glob 'php*'
Note, selecting 'php-swiftmailer' for glob 'php*'
Note, selecting 'php8.1-json' for glob 'php*'
Note, selecting 'php-gd2' for glob 'php*'
Note, selecting 'php-gmp' for glob 'php*'
Note, selecting 'php-symfony-translation-implementation' for glob 'php*'
Note, selecting 'phpdox' for glob 'php*'
Note, selecting 'php-tijsverkoyen-css-to-inline-styles' for glob 'php*'
Note, selecting 'php-text-template' for glob 'php*'
Note, selecting 'php-sebastian-resource-operations' for glob 'php*'
Note, selecting 'php-http-request' for glob 'php*'
Note, selecting 'php-symfony-property-info' for glob 'php*'
Note, selecting 'php8.1-pcov' for glob 'php*'
Note, selecting 'php5-imagick' for glob 'php*'
Note, selecting 'php-symfony-free-mobile-notifier' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-tripledes' for glob 'php*'
Note, selecting 'phpldapadmin' for glob 'php*'
Note, selecting 'php8.1-mongodb' for glob 'php*'
Note, selecting 'php8.1-readline' for glob 'php*'
Note, selecting 'php-symfony-mailjet-notifier' for glob 'php*'
Note, selecting 'php-symfony-yaml' for glob 'php*'
Note, selecting 'php-laminas-code' for glob 'php*'
Note, selecting 'php8.1-uuid' for glob 'php*'
Note, selecting 'php-pdo-mysql' for glob 'php*'
Note, selecting 'php-gmagick-all-dev' for glob 'php*'
Note, selecting 'php-twig-string-extra' for glob 'php*'
Note, selecting 'phppgadmin' for glob 'php*'
Note, selecting 'php-psr-http-client' for glob 'php*'
Note, selecting 'php-memcached-all-dev' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-rc4' for glob 'php*'
Note, selecting 'php-pdo-sqlite' for glob 'php*'
Note, selecting 'php-xml-htmlsax3' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-rsa' for glob 'php*'
Note, selecting 'php-loc' for glob 'php*'
Note, selecting 'php-log' for glob 'php*'
Note, selecting 'php-lua' for glob 'php*'
Note, selecting 'php8.1-phar' for glob 'php*'
Note, selecting 'php-lzf' for glob 'php*'
Note, selecting 'php-com-dotnet' for glob 'php*'
Note, selecting 'php8.1-pdo-dblib' for glob 'php*'
Note, selecting 'php-symfony-stopwatch' for glob 'php*'
Note, selecting 'php-mf2' for glob 'php*'
Note, selecting 'php8.1-sockets' for glob 'php*'
Note, selecting 'php8.1-ds' for glob 'php*'
Note, selecting 'php8.1-gd' for glob 'php*'
Note, selecting 'php8.1-ps' for glob 'php*'
Note, selecting 'php8.1-igbinary' for glob 'php*'
Note, selecting 'php-symfony-one-signal-notifier' for glob 'php*'
Note, selecting 'phploc' for glob 'php*'
Note, selecting 'php-netscape-bookmark-parser' for glob 'php*'
Note, selecting 'php5.6-common' for glob 'php*'
Note, selecting 'php-composer-spdx-licenses' for glob 'php*'
Note, selecting 'php-remctl' for glob 'php*'
Note, selecting 'php-pdo' for glob 'php*'
Note, selecting 'php-symfony-http-client-implementation' for glob 'php*'
Note, selecting 'php-pmd' for glob 'php*'
Note, selecting 'php-psr' for glob 'php*'
Note, selecting 'php-symfony-asset' for glob 'php*'
Note, selecting 'php-psr-http-message-implementation' for glob 'php*'
Note, selecting 'php8.1-uploadprogress' for glob 'php*'
Note, selecting 'php-egulias-email-validator' for glob 'php*'
Note, selecting 'php-mock-integration' for glob 'php*'
Note, selecting 'php-pdo-odbc' for glob 'php*'
Note, selecting 'php-symfony-messenger' for glob 'php*'
Note, selecting 'php-pnctl' for glob 'php*'
Note, selecting 'php-phpspec-prophecy' for glob 'php*'
Note, selecting 'php-gearman-all-dev' for glob 'php*'
Note, selecting 'php-rar' for glob 'php*'
Note, selecting 'php-mongodb' for glob 'php*'
Note, selecting 'php-mysql' for glob 'php*'
Note, selecting 'php-rrd' for glob 'php*'
Note, selecting 'php-symfony-fake-chat-notifier' for glob 'php*'
Note, selecting 'php-http-all-dev' for glob 'php*'
Note, selecting 'php-symfony-polyfill-util' for glob 'php*'
Note, selecting 'php-file-iterator' for glob 'php*'
Note, selecting 'php-phpmyadmin-shapefile' for glob 'php*'
Note, selecting 'php-doctrine-common' for glob 'php*'
Note, selecting 'php-mdb2-driver-mysqli' for glob 'php*'
Note, selecting 'php-letodms-core' for glob 'php*'
Note, selecting 'php-twig-extra-bundle' for glob 'php*'
Note, selecting 'php-symfony-polyfill-uuid' for glob 'php*'
Note, selecting 'php-symfony-postmark-mailer' for glob 'php*'
Note, selecting 'php-xcache' for glob 'php*'
Note, selecting 'php-crypt-blowfish' for glob 'php*'
Note, selecting 'php-luasandbox' for glob 'php*'
Note, selecting 'php-php-http-async-client-implementation' for glob 'php*'
Note, selecting 'php-uopz' for glob 'php*'
Note, selecting 'phpunit-exporter' for glob 'php*'
Note, selecting 'php-xmlrpc-all-dev' for glob 'php*'
Note, selecting 'php-phpdocumentor-reflection-docblock' for glob 'php*'
Note, selecting 'php-symfony-debug-bundle' for glob 'php*'
Note, selecting 'php-masterminds-html5' for glob 'php*'
Note, selecting 'php-doctrine-collections' for glob 'php*'
Note, selecting 'php-psr-all-dev' for glob 'php*'
Note, selecting 'php-xml' for glob 'php*'
Note, selecting 'php-json' for glob 'php*'
Note, selecting 'php-xsl' for glob 'php*'
Note, selecting 'php-symfony-string' for glob 'php*'
Note, selecting 'php-yac' for glob 'php*'
Note, selecting 'php-mime-type' for glob 'php*'
Note, selecting 'php7.4-common' for glob 'php*'
Note, selecting 'php-codecoverage' for glob 'php*'
Note, selecting 'php8.1-xmlreader' for glob 'php*'
Note, selecting 'php-symfony-esendex-notifier' for glob 'php*'
Note, selecting 'php-pcov' for glob 'php*'
Note, selecting 'php-zip' for glob 'php*'
Note, selecting 'php8.1-phpdbg' for glob 'php*'
Note, selecting 'php-vlucas-phpdotenv' for glob 'php*'
Note, selecting 'php-zmq' for glob 'php*'
Note, selecting 'php-symfony-polyfill-intl-icu' for glob 'php*'
Note, selecting 'php-symfony-polyfill-intl-idn' for glob 'php*'
Note, selecting 'php8.1-exif' for glob 'php*'
Note, selecting 'php5-cli' for glob 'php*'
Note, selecting 'php-symfony-nexmo-notifier' for glob 'php*'
Note, selecting 'php-shmop' for glob 'php*'
Note, selecting 'php-symfony-proxy-manager-bridge' for glob 'php*'
Note, selecting 'php-davedevelopment-hamcrest-php' for glob 'php*'
Note, selecting 'php-pear' for glob 'php*'
Note, selecting 'phpwebcounter' for glob 'php*'
Note, selecting 'php-symfony-spot-hit-notifier' for glob 'php*'
Note, selecting 'php-pcov-all-dev' for glob 'php*'
Note, selecting 'php-symfony-expression-language' for glob 'php*'
Note, selecting 'php-symfony-event-dispatcher-implementation' for glob 'php*'
Note, selecting 'php-uuid' for glob 'php*'
Note, selecting 'php-roundcube-rtf-html-php' for glob 'php*'
Note, selecting 'php-console-commandline' for glob 'php*'
Note, selecting 'php-opis-closure' for glob 'php*'
Note, selecting 'php-mysqlnd-ms' for glob 'php*'
Note, selecting 'php-symfony-password-hasher' for glob 'php*'
Note, selecting 'php-constant-time' for glob 'php*'
Note, selecting 'php-raphf-all-dev' for glob 'php*'
Note, selecting 'phpliteadmin-themes' for glob 'php*'
Note, selecting 'php-net-socket' for glob 'php*'
Note, selecting 'php5-fpm' for glob 'php*'
Note, selecting 'php-ast-all-dev' for glob 'php*'
Note, selecting 'php-phar' for glob 'php*'
Note, selecting 'php-psr-http-client-implementation' for glob 'php*'
Note, selecting 'php8.1-gettext' for glob 'php*'
Note, selecting 'php8.1-redis' for glob 'php*'
Note, selecting 'php8.1-sqlite3' for glob 'php*'
Note, selecting 'phpunit-complexity' for glob 'php*'
Note, selecting 'php-http-message-factory' for glob 'php*'
Note, selecting 'php7.1-common' for glob 'php*'
Note, selecting 'php-pda-pheanstalk' for glob 'php*'
Note, selecting 'php-zend-code' for glob 'php*'
Note, selecting 'php-league-flysystem-rackspace' for glob 'php*'
Note, selecting 'php-pear-frontend-gtk' for glob 'php*'
Note, selecting 'php-laminas-httphandlerrunner' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-random' for glob 'php*'
Note, selecting 'php-tideways' for glob 'php*'
Note, selecting 'php-twig-doc' for glob 'php*'
Note, selecting 'php-phpoption' for glob 'php*'
Note, selecting 'php-symfony-event-dispatcher' for glob 'php*'
Note, selecting 'php5-pgsql' for glob 'php*'
Note, selecting 'php-symfony-intl' for glob 'php*'
Note, selecting 'phpapi-20210902' for glob 'php*'
Note, selecting 'php-phpiredis' for glob 'php*'
Note, selecting 'php-php-mock-phpunit' for glob 'php*'
Note, selecting 'php-invoker' for glob 'php*'
Note, selecting 'php-memcached' for glob 'php*'
Note, selecting 'php-symfony-mattermost-notifier' for glob 'php*'
Note, selecting 'php-symfony-mailjet-mailer' for glob 'php*'
Note, selecting 'php-text-wiki' for glob 'php*'
Note, selecting 'php-symfony-http-foundation' for glob 'php*'
Note, selecting 'php-symfony-firebase-notifier' for glob 'php*'
Note, selecting 'php-services-weather' for glob 'php*'
Note, selecting 'php-hayageek-oauth2-yahoo' for glob 'php*'
Note, selecting 'php-sql-formatter' for glob 'php*'
Note, selecting 'php-thrift' for glob 'php*'
Note, selecting 'php-symfony-google-mailer' for glob 'php*'
Note, selecting 'php-symfony-web-link' for glob 'php*'
Note, selecting 'php-parsedown-extra' for glob 'php*'
Note, selecting 'php-symfony-mercure' for glob 'php*'
Note, selecting 'phpliteadmin' for glob 'php*'
Note, selecting 'php-aws-sdk' for glob 'php*'
Note, selecting 'php-token-stream' for glob 'php*'
Note, selecting 'php-symfony-polyfill' for glob 'php*'
Note, selecting 'php-sabre-vobject' for glob 'php*'
Note, selecting 'php-auth-sasl' for glob 'php*'
Note, selecting 'phpunit' for glob 'php*'
Note, selecting 'php-excimer' for glob 'php*'
Note, selecting 'php8.1-gearman' for glob 'php*'
Note, selecting 'php-symfony-turbo-sms-notifier' for glob 'php*'
Note, selecting 'php-exif' for glob 'php*'
Note, selecting 'php-bcmath' for glob 'php*'
Note, selecting 'php-ds-all-dev' for glob 'php*'
Note, selecting 'php-geshi' for glob 'php*'
Note, selecting 'php8.1-sybase' for glob 'php*'
Note, selecting 'php-league-flysystem-azure' for glob 'php*'
Note, selecting 'php-symfony-clickatell-notifier' for glob 'php*'
Note, selecting 'php-phpspec-prophecy-phpunit' for glob 'php*'
Note, selecting 'php5-xsl' for glob 'php*'
Note, selecting 'php-webmozart-assert' for glob 'php*'
Note, selecting 'php-numbers-words' for glob 'php*'
Note, selecting 'php-samyoul-u2f-php-server' for glob 'php*'
Note, selecting 'php-symfony-inflector' for glob 'php*'
Note, selecting 'php8.1-pdo-odbc' for glob 'php*'
Note, selecting 'php-pear-frontend-web' for glob 'php*'
Note, selecting 'php-crypt-gpg' for glob 'php*'
Note, selecting 'php-libvirt-php' for glob 'php*'
Note, selecting 'php-net-smtp' for glob 'php*'
Note, selecting 'php-zeroc-ice' for glob 'php*'
Note, selecting 'php-symfony' for glob 'php*'
Note, selecting 'php-tcpdf' for glob 'php*'
Note, selecting 'php8.1-ast' for glob 'php*'
Note, selecting 'php-symfony-loco-translation-provider' for glob 'php*'
Note, selecting 'php-semsol-arc2' for glob 'php*'
Note, selecting 'php-scrutinizer-ocular' for glob 'php*'
Note, selecting 'php-symfony-octopush-notifier' for glob 'php*'
Note, selecting 'php-gearman' for glob 'php*'
Note, selecting 'php8.1-bz2' for glob 'php*'
Note, selecting 'php-parsedown' for glob 'php*'
Note, selecting 'php8.1-cgi' for glob 'php*'
Note, selecting 'php-console-getopt' for glob 'php*'
Note, selecting 'php8.1-cli' for glob 'php*'
Note, selecting 'php-enqueue-messenger-adapter' for glob 'php*'
Note, selecting 'php8.1-dba' for glob 'php*'
Note, selecting 'php8.1-dev' for glob 'php*'
Note, selecting 'php8.1-dom' for glob 'php*'
Note, selecting 'php-doctrine-mongodb-odm' for glob 'php*'
Note, selecting 'php-cache' for glob 'php*'
Note, selecting 'php-symfony-uid' for glob 'php*'
Note, selecting 'php-bacon-qr-code' for glob 'php*'
Note, selecting 'php-symfony-amazon-sqs-messenger' for glob 'php*'
Note, selecting 'php8.1-ffi' for glob 'php*'
Note, selecting 'php-doctrine-deprecations' for glob 'php*'
Note, selecting 'php8.1-fpm' for glob 'php*'
Note, selecting 'php8.1-ftp' for glob 'php*'
Note, selecting 'php-autoload' for glob 'php*'
Note, selecting 'php-mdb2-driver-querysim' for glob 'php*'
Note, selecting 'php8.1-ldap' for glob 'php*'
Note, selecting 'php8.1-gmp' for glob 'php*'
Note, selecting 'php-doctrine-reflection' for glob 'php*'
Note, selecting 'php-symfony-sendinblue-notifier' for glob 'php*'
Note, selecting 'php-recode' for glob 'php*'
Note, selecting 'php-rrd-all-dev' for glob 'php*'
Note, selecting 'php-yac-all-dev' for glob 'php*'
Note, selecting 'php-phar-io-manifest' for glob 'php*'
Note, selecting 'php-symfony-crowdin-translation-provider' for glob 'php*'
Note, selecting 'php-symfony-workflow' for glob 'php*'
Note, selecting 'php-symfony-sms-biuras-notifier' for glob 'php*'
Note, selecting 'php-psr-http-factory-implementation' for glob 'php*'
Note, selecting 'php8.1-sysvmsg' for glob 'php*'
Note, selecting 'php-redis-all-dev' for glob 'php*'
Note, selecting 'php-font-lib' for glob 'php*'
Note, selecting 'php-composer-pcre' for glob 'php*'
Note, selecting 'php-doctrine-phpcr-odm' for glob 'php*'
Note, selecting 'php-symfony-rocket-chat-notifier' for glob 'php*'
Note, selecting 'php8.1-xmlwriter' for glob 'php*'
Note, selecting 'php-sockets' for glob 'php*'
Note, selecting 'php5-sqlite' for glob 'php*'
Note, selecting 'php-memcache-all-dev' for glob 'php*'
Note, selecting 'php-psr-event-dispatcher-implementation' for glob 'php*'
Note, selecting 'php-radius' for glob 'php*'
Note, selecting 'php-symfony-mailchimp-mailer' for glob 'php*'
Note, selecting 'php-async-aws-ses' for glob 'php*'
Note, selecting 'php-async-aws-sns' for glob 'php*'
Note, selecting 'php-async-aws-sqs' for glob 'php*'
Note, selecting 'php-xml-util' for glob 'php*'
Note, selecting 'php-symfony-telnyx-notifier' for glob 'php*'
Note, selecting 'php-league-oauth2-google' for glob 'php*'
Note, selecting 'php-stomp' for glob 'php*'
Note, selecting 'php-seclib' for glob 'php*'
Note, selecting 'php8.1-amqp' for glob 'php*'
Note, selecting 'php-league-flysystem-sftp' for glob 'php*'
Note, selecting 'php-doctrine-persistence' for glob 'php*'
Note, selecting 'php-laminas-stdlib' for glob 'php*'
Note, selecting 'php-symfony-sendinblue-mailer' for glob 'php*'
Note, selecting 'php-timer' for glob 'php*'
Note, selecting 'php-shellcommand' for glob 'php*'
Note, selecting 'php8.1-pdo' for glob 'php*'
Note, selecting 'php-posix' for glob 'php*'
Note, selecting 'php-sqlite' for glob 'php*'
Note, selecting 'php8.1-psr' for glob 'php*'
Note, selecting 'php8.1-sysvsem' for glob 'php*'
Note, selecting 'php8.1-sysvshm' for glob 'php*'
Note, selecting 'phpsysinfo' for glob 'php*'
Note, selecting 'php-net-nntp' for glob 'php*'
Note, selecting 'php8.1-apcu' for glob 'php*'
Note, selecting 'php-myclabs-deep-copy' for glob 'php*'
Note, selecting 'php-zeta-unit-test' for glob 'php*'
Note, selecting 'php-facedetect' for glob 'php*'
Note, selecting 'php-xmlreader' for glob 'php*'
Note, selecting 'php8.1-rrd' for glob 'php*'
Note, selecting 'php-symfony-mercure-notifier' for glob 'php*'
Note, selecting 'php8.1-xdebug' for glob 'php*'
Note, selecting 'php-fpdf' for glob 'php*'
Note, selecting 'php-sysvmsg' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-blowfish' for glob 'php*'
Note, selecting 'php-phpdocumentor-type-resolver' for glob 'php*'
Note, selecting 'php-phpseclib-crypt-rijndael' for glob 'php*'
Note, selecting 'php-symfony-gateway-api-notifier' for glob 'php*'
Note, selecting 'php-lorenzo-pinky' for glob 'php*'
Note, selecting 'php-google-recaptcha' for glob 'php*'
Note, selecting 'php5-mysql' for glob 'php*'
Note, selecting 'php-pragmarx-google2fa-qrcode' for glob 'php*'
Note, selecting 'php-symfony-doctrine-messenger' for glob 'php*'
Note, selecting 'php-xml-svg' for glob 'php*'
Note, selecting 'php-all-dev' for glob 'php*'
Note, selecting 'php-psr-container-implementation' for glob 'php*'
Note, selecting 'php7.0-curl' for glob 'php*'
Note, selecting 'php-net-idna' for glob 'php*'
Note, selecting 'php-symfony-finder' for glob 'php*'
Note, selecting 'php-guestfs' for glob 'php*'
Note, selecting 'php-php-gettext' for glob 'php*'
Note, selecting 'php8.1-pdo-pgsql' for glob 'php*'
Note, selecting 'php-mock-phpunit' for glob 'php*'
Note, selecting 'php8.1-xml' for glob 'php*'
Note, selecting 'php-zend-eventmanager' for glob 'php*'
Note, selecting 'php8.1-xsl' for glob 'php*'
Note, selecting 'php-ps-all-dev' for glob 'php*'
Note, selecting 'php-symfony-polyfill-mbstring' for glob 'php*'
Note, selecting 'php-symfony-all-my-sms-notifier' for glob 'php*'
Note, selecting 'php8.1-yac' for glob 'php*'
Note, selecting 'php-ldap' for glob 'php*'
Note, selecting 'php-elisp' for glob 'php*'
Note, selecting 'php-sysvsem' for glob 'php*'
Note, selecting 'php-symfony-rate-limiter' for glob 'php*'
Note, selecting 'php-sysvshm' for glob 'php*'
Note, selecting 'php-symfony-yunpian-notifier' for glob 'php*'
Note, selecting 'php8.1-zip' for glob 'php*'
Note, selecting 'php8.1-zmq' for glob 'php*'
Note, selecting 'php-symfony-polyfill-apcu' for glob 'php*'
Note, selecting 'php-twig-inky-extra' for glob 'php*'
Note, selecting 'php-endroid-qr-code' for glob 'php*'
Note, selecting 'php-mockery' for glob 'php*'
Note, selecting 'php8.1-tokenizer' for glob 'php*'
Note, selecting 'php-fxsl' for glob 'php*'
Note, selecting 'php-doctrine-sql-formatter' for glob 'php*'
Note, selecting 'php-ruflin-elastica' for glob 'php*'
Note, selecting 'php8.1-pdo-firebird' for glob 'php*'
Note, selecting 'php-ramsey-uuid-console' for glob 'php*'
Note, selecting 'php-wfio' for glob 'php*'
Note, selecting 'php8.1-oauth' for glob 'php*'
Note, selecting 'php5-curl' for glob 'php*'
Note, selecting 'php-symfony-css-selector' for glob 'php*'
Note, selecting 'php-sqlite3' for glob 'php*'
Note, selecting 'php-symfony-validator' for glob 'php*'
Note, selecting 'php-symfony-polyfill-intl-grapheme' for glob 'php*'
Note, selecting 'php-net-imap' for glob 'php*'
Note, selecting 'php-amqp' for glob 'php*'
Note, selecting 'php-symfony-filesystem' for glob 'php*'
Package 'php-lua' is not installed, so not removed
Package 'php-mysqlnd-ms' is not installed, so not removed
Package 'php-radius' is not installed, so not removed
Package 'php-stomp' is not installed, so not removed
Package 'php5.6-common' is not installed, so not removed
Package 'php5.6-json' is not installed, so not removed
Package 'php7.0-common' is not installed, so not removed
Package 'php7.1-common' is not installed, so not removed
Package 'php7.2-common' is not installed, so not removed
Package 'php7.3-common' is not installed, so not removed
Package 'php7.4-common' is not installed, so not removed
Package 'php8.0-common' is not installed, so not removed
Package 'php-pear-frontend-gtk' is not installed, so not removed
Package 'php-pear-frontend-web' is not installed, so not removed
Note, selecting 'php-pear' instead of 'php-console-getopt'
Note, selecting 'php-pear' instead of 'php-structures-graph'
Note, selecting 'php-pear' instead of 'php-xml-util'
Package 'php7.0-curl' is not installed, so not removed
Package 'php7.2-sodium' is not installed, so not removed
Note, selecting 'php8.1-common' instead of 'php-calendar'
Note, selecting 'php8.1-common' instead of 'php-ctype'
Note, selecting 'php8.1-common' instead of 'php-exif'
Note, selecting 'php8.1-common' instead of 'php-ffi'
Note, selecting 'php8.1-common' instead of 'php-fileinfo'
Note, selecting 'php8.1-common' instead of 'php-ftp'
Note, selecting 'php8.1-common' instead of 'php-iconv'
Note, selecting 'php8.1-common' instead of 'php-pdo'
Note, selecting 'php8.1-common' instead of 'php-phar'
Note, selecting 'php8.1-common' instead of 'php-posix'
Note, selecting 'php8.1-common' instead of 'php-shmop'
Note, selecting 'php8.1-common' instead of 'php-sockets'
Note, selecting 'php8.1-common' instead of 'php-sysvmsg'
Note, selecting 'php8.1-common' instead of 'php-sysvsem'
Note, selecting 'php8.1-common' instead of 'php-sysvshm'
Note, selecting 'php8.1-common' instead of 'php8.1-calendar'
Note, selecting 'php8.1-common' instead of 'php8.1-ctype'
Note, selecting 'php8.1-common' instead of 'php8.1-exif'
Note, selecting 'php8.1-common' instead of 'php8.1-ffi'
Note, selecting 'php8.1-common' instead of 'php8.1-fileinfo'
Note, selecting 'php8.1-common' instead of 'php8.1-ftp'
Note, selecting 'php8.1-common' instead of 'php8.1-gettext'
Note, selecting 'php8.1-common' instead of 'php8.1-iconv'
Note, selecting 'php8.1-common' instead of 'php8.1-pdo'
Note, selecting 'php8.1-common' instead of 'php8.1-phar'
Note, selecting 'php8.1-common' instead of 'php8.1-posix'
Note, selecting 'php8.1-common' instead of 'php8.1-shmop'
Note, selecting 'php8.1-common' instead of 'php8.1-sockets'
Note, selecting 'php8.1-common' instead of 'php8.1-sysvmsg'
Note, selecting 'php8.1-common' instead of 'php8.1-sysvsem'
Note, selecting 'php8.1-common' instead of 'php8.1-sysvshm'
Note, selecting 'php8.1-common' instead of 'php8.1-tokenizer'
Note, selecting 'php8.1-mysql' instead of 'php-mysqli'
Note, selecting 'php8.1-mysql' instead of 'php-mysqlnd'
Note, selecting 'php8.1-mysql' instead of 'php-pdo-mysql'
Note, selecting 'php8.1-mysql' instead of 'php8.1-mysqli'
Note, selecting 'php8.1-mysql' instead of 'php8.1-mysqlnd'
Note, selecting 'php8.1-mysql' instead of 'php8.1-pdo-mysql'
Note, selecting 'php8.1-odbc' instead of 'php-pdo-odbc'
Note, selecting 'php8.1-odbc' instead of 'php8.1-pdo-odbc'
Note, selecting 'php8.1-opcache' instead of 'php-opcache'
Note, selecting 'php8.1-pgsql' instead of 'php-pdo-pgsql'
Note, selecting 'php8.1-pgsql' instead of 'php8.1-pdo-pgsql'
Note, selecting 'php8.1-sqlite3' instead of 'php-pdo-sqlite'
Note, selecting 'php8.1-sqlite3' instead of 'php8.1-pdo-sqlite'
Note, selecting 'php8.1-xml' instead of 'php-dom'
Note, selecting 'php8.1-xml' instead of 'php-simplexml'
Note, selecting 'php8.1-xml' instead of 'php-xmlreader'
Note, selecting 'php8.1-xml' instead of 'php-xmlwriter'
Note, selecting 'php8.1-xml' instead of 'php-xsl'
Note, selecting 'php8.1-xml' instead of 'php8.1-dom'
Note, selecting 'php8.1-xml' instead of 'php8.1-simplexml'
Note, selecting 'php8.1-xml' instead of 'php8.1-xmlreader'
Note, selecting 'php8.1-xml' instead of 'php8.1-xmlwriter'
Package 'php5-cli' is not installed, so not removed
Package 'php5-curl' is not installed, so not removed
Package 'php-mcrypt' is not installed, so not removed
Package 'php5-mysql' is not installed, so not removed
Package 'php5-pgsql' is not installed, so not removed
Package 'php5-sqlite' is not installed, so not removed
Package 'php5' is not installed, so not removed
Package 'php5-ldap' is not installed, so not removed
Note, selecting 'elpa-php-mode' instead of 'php-elisp'
Package 'php-mapscript' is not installed, so not removed
Package 'php-apc' is not installed, so not removed
Package 'php-suhosin' is not installed, so not removed
Package 'php5-fpm' is not installed, so not removed
Package 'php-hayageek-oauth2-yahoo' is not installed, so not removed
Package 'php-league-oauth2-google' is not installed, so not removed
Package 'php-stevenmaguire-oauth2-microsoft' is not installed, so not removed
Package 'phpphylotree' is not installed, so not removed
Note, selecting 'pdepend' instead of 'php-depend'
Note, selecting 'pdepend' instead of 'php-pdepend'
Package 'php-xcache' is not installed, so not removed
Package 'php-async-aws-s3' is not installed, so not removed
Note, selecting 'php-codecoverage' instead of 'phpunit-php-code-coverage'
Package 'php-console-color2' is not installed, so not removed
Note, selecting 'php-deepcopy' instead of 'php-myclabs-deep-copy'
Package 'php-alcaeus-mongo-php-adapter' is not installed, so not removed
Package 'php-doctrine-phpcr-odm' is not installed, so not removed
Package 'php-doctrine-mongodb-odm' is not installed, so not removed
Package 'php-ml-json-ld' is not installed, so not removed
Package 'php-semsol-arc2' is not installed, so not removed
Note, selecting 'php-email-validator' instead of 'php-egulias-email-validator'
Package 'php-com-dotnet' is not installed, so not removed
Package 'php-rar' is not installed, so not removed
Package 'php-laminas-httphandlerrunner' is not installed, so not removed
Package 'php-cordoval-hamcrest-php' is not installed, so not removed
Package 'php-davedevelopment-hamcrest-php' is not installed, so not removed
Package 'php-kodova-hamcrest-php' is not installed, so not removed
Package 'php-scrutinizer-ocular' is not installed, so not removed
Package 'php-league-flysystem-sftp' is not installed, so not removed
Package 'php-league-flysystem-eventable-filesystem' is not installed, so not removed
Package 'php-league-flysystem-rackspace' is not installed, so not removed
Package 'php-league-flysystem-azure' is not installed, so not removed
Package 'php-league-flysystem-webdav' is not installed, so not removed
Package 'php-league-flysystem-aws-s3-v2' is not installed, so not removed
Package 'php-league-flysystem-aws-s3-v3' is not installed, so not removed
Package 'php-spatie-flysystem-dropbox' is not installed, so not removed
Package 'php-srmklive-flysystem-dropbox-v2' is not installed, so not removed
Package 'php-league-flysystem-cached-adapter' is not installed, so not removed
Package 'php-league-flysystem-ziparchive' is not installed, so not removed
Package 'php-sqlite' is not installed, so not removed
Package 'php-lzf' is not installed, so not removed
Package 'php-pnctl' is not installed, so not removed
Package 'php-mdb2-driver-fbsql' is not installed, so not removed
Package 'php-mdb2-driver-ibase' is not installed, so not removed
Package 'php-mdb2-driver-mssql' is not installed, so not removed
Package 'php-mdb2-driver-mysqli' is not installed, so not removed
Package 'php-mdb2-driver-oci8' is not installed, so not removed
Package 'php-mdb2-driver-odbc' is not installed, so not removed
Package 'php-mdb2-driver-querysim' is not installed, so not removed
Package 'php-mdb2-driver-sqlite' is not installed, so not removed
Package 'php-mdb2-driver-sqlsrv' is not installed, so not removed
Package 'php-barnabywalters-mf-cleaner' is not installed, so not removed
Package 'php-php-mock-phpunit' is not installed, so not removed
Package 'php-graylog2-gelf-php' is not installed, so not removed
Package 'php-doctrine-couchdb' is not installed, so not removed
Package 'php-ruflin-elastica' is not installed, so not removed
Package 'php-elasticsearch' is not installed, so not removed
Package 'php-aws-sdk' is not installed, so not removed
Package 'php-rollbar' is not installed, so not removed
Package 'php-console' is not installed, so not removed
Note, selecting 'php-nyholm-psr7' instead of 'php-psr-http-factory-implementation'
Package 'php-wfio' is not installed, so not removed
Package 'php-dbase' is not installed, so not removed
Package 'php-libsodium' is not installed, so not removed
Package 'php-phpiredis' is not installed, so not removed
Note, selecting 'php-zend-code' instead of 'php-laminas-code'
Note, selecting 'php-zend-stdlib' instead of 'php-laminas-stdlib'
Package 'php-ocramius-proxy-manager' is not installed, so not removed
Package 'php-zendframework-zend-stdlib' is not installed, so not removed
Note, selecting 'php-proxy-manager' instead of 'php-friendsofphp-proxy-manager-lts'
Package 'php-rhumsaa-uuid' is not installed, so not removed
Package 'php-moontoast-math' is not installed, so not removed
Package 'php-ramsey-uuid-console' is not installed, so not removed
Package 'php-ramsey-uuid-doctrine' is not installed, so not removed
Package 'php-paragonie-random-lib' is not installed, so not removed
Note, selecting 'php-sass' instead of 'php8.1-sass'
Note, selecting 'php-seclib' instead of 'php-math-biginteger'
Package 'php-crypt-blowfish' is not installed, so not removed
Package 'php-compat' is not installed, so not removed
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-aes'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-base'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-blowfish'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-des'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-hash'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-random'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-rc4'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-rijndael'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-rsa'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-tripledes'
Note, selecting 'php-seclib' instead of 'php-phpseclib-crypt-twofish'
Note, selecting 'php-seclib' instead of 'php-phpseclib-file-ansi'
Note, selecting 'php-seclib' instead of 'php-phpseclib-file-asn1'
Note, selecting 'php-seclib' instead of 'php-phpseclib-file-x509'
Note, selecting 'php-seclib' instead of 'php-phpseclib-math-biginteger'
Note, selecting 'php-seclib' instead of 'php-phpseclib-net-sftp'
Note, selecting 'php-seclib' instead of 'php-phpseclib-net-ssh1'
Note, selecting 'php-seclib' instead of 'php-phpseclib-net-ssh2'
Note, selecting 'php-seclib' instead of 'php-phpseclib-system-ssh-agent'
Package 'php-cache' is not installed, so not removed
Package 'php-xml-serializer' is not installed, so not removed
Note, selecting 'php-sql-formatter' instead of 'php-doctrine-sql-formatter'
Package 'php-enqueue-messenger-adapter' is not installed, so not removed
Package 'php-numbers-words' is not installed, so not removed
Package 'php7.0-thrift' is not installed, so not removed
Package 'php7.2-thrift' is not installed, so not removed
Package 'php-net-idna' is not installed, so not removed
Package 'php-phpstan' is not installed, so not removed
Package 'php-vimeo-psalm' is not installed, so not removed
Package 'php-zendframework-zend-eventmanager' is not installed, so not removed
Package 'php-container-interop' is not installed, so not removed
Note, selecting 'php-zend-eventmanager' instead of 'php-laminas-eventmanager'
Note, selecting 'php8.1-dba' instead of 'php-dba'
Note, selecting 'php8.1-interbase' instead of 'php-pdo-firebird'
Note, selecting 'php8.1-interbase' instead of 'php8.1-pdo-firebird'
Note, selecting 'php8.1-sybase' instead of 'php-pdo-dblib'
Note, selecting 'php8.1-sybase' instead of 'php8.1-pdo-dblib'
Note, selecting 'phpab' instead of 'php-autoload'
Note, selecting 'phpcpd' instead of 'php-cpd'
Note, selecting 'phploc' instead of 'php-loc'
Note, selecting 'phpmd' instead of 'php-pmd'
Package 'php-recode' is not installed, so not removed
Package 'php-gd2' is not installed, so not removed
Package 'php-pragmarx-google2fa-qrcode' is not installed, so not removed
Package 'php-samyoul-u2f-php-server' is not installed, so not removed
Package 'php5-xsl' is not installed, so not removed
Note, selecting 'phpunit-resource-operations' instead of 'php-sebastian-resource-operations'
Package 'php5-imagick' is not installed, so not removed
Package 'php-endroid-qr-code' is not installed, so not removed
Package 'php-guzzlehttp-guzzle' is not installed, so not removed
Package 'php-bjeavons-zxcvbn-php' is not installed, so not removed
Package 'php7.4-fpm' is not installed, so not removed
Package 'php-all-dev' is not installed, so not removed
Package 'php-cgi' is not installed, so not removed
Package 'php-cli' is not installed, so not removed
Package 'php-curl' is not installed, so not removed
Package 'php-dev' is not installed, so not removed
Package 'php-gd' is not installed, so not removed
Package 'php-gmp' is not installed, so not removed
Package 'php-json' is not installed, so not removed
Package 'php-ldap' is not installed, so not removed
Package 'php-odbc' is not installed, so not removed
Package 'php-pear' is not installed, so not removed
Package 'php-pgsql' is not installed, so not removed
Package 'php-pspell' is not installed, so not removed
Package 'php-snmp' is not installed, so not removed
Package 'php-sqlite3' is not installed, so not removed
Package 'php-tidy' is not installed, so not removed
Package 'php-xml' is not installed, so not removed
Package 'php-amqp' is not installed, so not removed
Package 'php-amqp-all-dev' is not installed, so not removed
Package 'php-amqplib' is not installed, so not removed
Package 'php-apcu' is not installed, so not removed
Package 'php-apcu-all-dev' is not installed, so not removed
Package 'php-arthurhoaro-web-thumbnailer' is not installed, so not removed
Package 'php-ast' is not installed, so not removed
Package 'php-ast-all-dev' is not installed, so not removed
Package 'php-async-aws-core' is not installed, so not removed
Package 'php-async-aws-ses' is not installed, so not removed
Package 'php-async-aws-sns' is not installed, so not removed
Package 'php-async-aws-sqs' is not installed, so not removed
Package 'php-auth-sasl' is not installed, so not removed
Package 'php-bacon-qr-code' is not installed, so not removed
Package 'php-bcmath' is not installed, so not removed
Package 'php-bz2' is not installed, so not removed
Package 'php-cache-integration-tests' is not installed, so not removed
Package 'php-cache-lite' is not installed, so not removed
Package 'php-cache-tag-interop' is not installed, so not removed
Package 'php-cas' is not installed, so not removed
Package 'php-codecoverage' is not installed, so not removed
Package 'php-codesniffer' is not installed, so not removed
Package 'php-composer-ca-bundle' is not installed, so not removed
Package 'php-composer-metadata-minifier' is not installed, so not removed
Package 'php-composer-pcre' is not installed, so not removed
Package 'php-composer-semver' is not installed, so not removed
Package 'php-composer-spdx-licenses' is not installed, so not removed
Package 'php-composer-xdebug-handler' is not installed, so not removed
Package 'php-console-commandline' is not installed, so not removed
Package 'php-console-table' is not installed, so not removed
Package 'php-constant-time' is not installed, so not removed
Package 'php-crypt-gpg' is not installed, so not removed
Package 'php-dapphp-radius' is not installed, so not removed
Package 'php-dasprid-enum' is not installed, so not removed
Package 'php-date' is not installed, so not removed
Package 'php-db' is not installed, so not removed
Package 'php-deepcopy' is not installed, so not removed
Package 'php-directory-scanner' is not installed, so not removed
Package 'php-doctrine-annotations' is not installed, so not removed
Package 'php-doctrine-cache' is not installed, so not removed
Package 'php-doctrine-collections' is not installed, so not removed
Package 'php-doctrine-common' is not installed, so not removed
Package 'php-doctrine-data-fixtures' is not installed, so not removed
Package 'php-doctrine-dbal' is not installed, so not removed
Package 'php-doctrine-deprecations' is not installed, so not removed
Package 'php-doctrine-event-manager' is not installed, so not removed
Package 'php-doctrine-inflector' is not installed, so not removed
Package 'php-doctrine-instantiator' is not installed, so not removed
Package 'php-doctrine-lexer' is not installed, so not removed
Package 'php-doctrine-orm' is not installed, so not removed
Package 'php-doctrine-persistence' is not installed, so not removed
Package 'php-doctrine-reflection' is not installed, so not removed
Package 'php-dompdf' is not installed, so not removed
Package 'php-dragonmantank-cron-expression' is not installed, so not removed
Package 'php-ds' is not installed, so not removed
Package 'php-ds-all-dev' is not installed, so not removed
Package 'php-easyrdf' is not installed, so not removed
Package 'php-email-validator' is not installed, so not removed
Package 'php-enchant' is not installed, so not removed
Package 'php-excimer' is not installed, so not removed
Package 'php-facedetect' is not installed, so not removed
Package 'php-fdomdocument' is not installed, so not removed
Package 'php-fig-link-util' is not installed, so not removed
Package 'php-file-iterator' is not installed, so not removed
Package 'php-finder-facade' is not installed, so not removed
Package 'php-finder-facade-doc' is not installed, so not removed
Package 'php-font-lib' is not installed, so not removed
Package 'php-fpdf' is not installed, so not removed
Package 'php-fpm' is not installed, so not removed
Package 'php-fxsl' is not installed, so not removed
Package 'php-gearman' is not installed, so not removed
Package 'php-gearman-all-dev' is not installed, so not removed
Package 'php-geos' is not installed, so not removed
Package 'php-geshi' is not installed, so not removed
Package 'php-getallheaders' is not installed, so not removed
Package 'php-getid3' is not installed, so not removed
Package 'php-gettext-languages' is not installed, so not removed
Package 'php-gmagick' is not installed, so not removed
Package 'php-gmagick-all-dev' is not installed, so not removed
Package 'php-gnupg' is not installed, so not removed
Package 'php-gnupg-all-dev' is not installed, so not removed
Package 'php-google-recaptcha' is not installed, so not removed
Package 'php-guestfs' is not installed, so not removed
Package 'php-guzzlehttp-promises' is not installed, so not removed
Package 'php-guzzlehttp-psr7' is not installed, so not removed
Package 'php-hamcrest' is not installed, so not removed
Package 'php-htmlawed' is not installed, so not removed
Package 'php-htmlpurifier' is not installed, so not removed
Package 'php-http' is not installed, so not removed
Package 'php-http-all-dev' is not installed, so not removed
Package 'php-http-httplug' is not installed, so not removed
Package 'php-http-interop-http-factory-tests' is not installed, so not removed
Package 'php-http-message-factory' is not installed, so not removed
Package 'php-http-promise' is not installed, so not removed
Package 'php-http-psr7-integration-tests' is not installed, so not removed
Package 'php-http-request' is not installed, so not removed
Package 'php-http-request2' is not installed, so not removed
Package 'php-http-webdav-server' is not installed, so not removed
Package 'php-httpful' is not installed, so not removed
Package 'php-icinga' is not installed, so not removed
Package 'php-igbinary' is not installed, so not removed
Package 'php-igbinary-all-dev' is not installed, so not removed
Package 'php-image-text' is not installed, so not removed
Package 'php-imagick' is not installed, so not removed
Package 'php-imagick-all-dev' is not installed, so not removed
Package 'php-imap' is not installed, so not removed
Package 'php-interbase' is not installed, so not removed
Package 'php-intl' is not installed, so not removed
Package 'php-invoker' is not installed, so not removed
Package 'php-json-schema' is not installed, so not removed
Package 'php-klogger' is not installed, so not removed
Package 'php-league-commonmark' is not installed, so not removed
Package 'php-league-flysystem' is not installed, so not removed
Package 'php-league-html-to-markdown' is not installed, so not removed
Package 'php-league-mime-type-detection' is not installed, so not removed
Package 'php-letodms-core' is not installed, so not removed
Package 'php-libvirt-php' is not installed, so not removed
Package 'php-log' is not installed, so not removed
Package 'php-lorenzo-pinky' is not installed, so not removed
Package 'php-luasandbox' is not installed, so not removed
Package 'php-mail' is not installed, so not removed
Package 'php-mail-mime' is not installed, so not removed
Package 'php-mailparse' is not installed, so not removed
Package 'php-mailparse-all-dev' is not installed, so not removed
Package 'php-malkusch-lock' is not installed, so not removed
Package 'php-mapi' is not installed, so not removed
Package 'php-mariadb-mysql-kbs' is not installed, so not removed
Package 'php-masterminds-html5' is not installed, so not removed
Package 'php-mbstring' is not installed, so not removed
Package 'php-mdb2' is not installed, so not removed
Package 'php-mdb2-driver-mysql' is not installed, so not removed
Package 'php-mdb2-driver-pgsql' is not installed, so not removed
Package 'php-memcache' is not installed, so not removed
Package 'php-memcache-all-dev' is not installed, so not removed
Package 'php-memcached' is not installed, so not removed
Package 'php-memcached-all-dev' is not installed, so not removed
Package 'php-mf2' is not installed, so not removed
Package 'php-mikey179-vfsstream' is not installed, so not removed
Package 'php-mime-type' is not installed, so not removed
Package 'php-mock' is not installed, so not removed
Package 'php-mock-integration' is not installed, so not removed
Package 'php-mock-phpunit' is not installed, so not removed
Package 'php-mockery' is not installed, so not removed
Package 'php-mockery-doc' is not installed, so not removed
Package 'php-mongodb' is not installed, so not removed
Package 'php-mongodb-all-dev' is not installed, so not removed
Package 'php-monolog' is not installed, so not removed
Package 'php-msgpack' is not installed, so not removed
Package 'php-msgpack-all-dev' is not installed, so not removed
Package 'php-net-dime' is not installed, so not removed
Package 'php-net-dns2' is not installed, so not removed
Package 'php-net-ftp' is not installed, so not removed
Package 'php-net-imap' is not installed, so not removed
Package 'php-net-ipv6' is not installed, so not removed
Package 'php-net-ldap2' is not installed, so not removed
Package 'php-net-ldap3' is not installed, so not removed
Package 'php-net-nntp' is not installed, so not removed
Package 'php-net-publicsuffix' is not installed, so not removed
Package 'php-net-sieve' is not installed, so not removed
Package 'php-net-smtp' is not installed, so not removed
Package 'php-net-socket' is not installed, so not removed
Package 'php-net-url' is not installed, so not removed
Package 'php-net-url2' is not installed, so not removed
Package 'php-net-whois' is not installed, so not removed
Package 'php-netscape-bookmark-parser' is not installed, so not removed
Package 'php-nikic-fast-route' is not installed, so not removed
Package 'php-nrk-predis' is not installed, so not removed
Package 'php-nyholm-psr7' is not installed, so not removed
Package 'php-oauth' is not installed, so not removed
Package 'php-oauth-all-dev' is not installed, so not removed
Package 'php-opis-closure' is not installed, so not removed
Package 'php-parsedown' is not installed, so not removed
Package 'php-parsedown-extra' is not installed, so not removed
Package 'php-parser' is not installed, so not removed
Package 'php-patchwork-utf8' is not installed, so not removed
Package 'php-pclzip' is not installed, so not removed
Package 'php-pcov' is not installed, so not removed
Package 'php-pcov-all-dev' is not installed, so not removed
Package 'php-pda-pheanstalk' is not installed, so not removed
Package 'php-phar-io-manifest' is not installed, so not removed
Package 'php-phar-io-version' is not installed, so not removed
Package 'php-php-gettext' is not installed, so not removed
Package 'php-phpdbg' is not installed, so not removed
Package 'php-phpdocumentor-reflection-common' is not installed, so not removed
Package 'php-phpdocumentor-reflection-docblock' is not installed, so not removed
Package 'php-phpdocumentor-type-resolver' is not installed, so not removed
Package 'php-phpmyadmin-motranslator' is not installed, so not removed
Package 'php-phpmyadmin-shapefile' is not installed, so not removed
Package 'php-phpmyadmin-sql-parser' is not installed, so not removed
Package 'php-phpoption' is not installed, so not removed
Package 'php-phpseclib' is not installed, so not removed
Package 'php-phpseclib3' is not installed, so not removed
Package 'php-phpspec-prophecy' is not installed, so not removed
Package 'php-phpspec-prophecy-phpunit' is not installed, so not removed
Package 'php-phpstan-phpdoc-parser' is not installed, so not removed
Package 'php-predis' is not installed, so not removed
Package 'php-proxy-manager' is not installed, so not removed
Package 'php-ps' is not installed, so not removed
Package 'php-ps-all-dev' is not installed, so not removed
Package 'php-psr' is not installed, so not removed
Package 'php-psr-all-dev' is not installed, so not removed
Package 'php-psr-cache' is not installed, so not removed
Package 'php-psr-container' is not installed, so not removed
Package 'php-psr-event-dispatcher' is not installed, so not removed
Package 'php-psr-http-client' is not installed, so not removed
Package 'php-psr-http-factory' is not installed, so not removed
Package 'php-psr-http-message' is not installed, so not removed
Package 'php-psr-link' is not installed, so not removed
Package 'php-psr-log' is not installed, so not removed
Package 'php-psr-simple-cache' is not installed, so not removed
Package 'php-pubsubhubbub-publisher' is not installed, so not removed
Package 'php-ramsey-uuid' is not installed, so not removed
Package 'php-random-compat' is not installed, so not removed
Package 'php-raphf' is not installed, so not removed
Package 'php-raphf-all-dev' is not installed, so not removed
Package 'php-react-promise' is not installed, so not removed
Package 'php-readline' is not installed, so not removed
Package 'php-redis' is not installed, so not removed
Package 'php-redis-all-dev' is not installed, so not removed
Package 'php-remctl' is not installed, so not removed
Package 'php-roundcube-rtf-html-php' is not installed, so not removed
Package 'php-rrd' is not installed, so not removed
Package 'php-rrd-all-dev' is not installed, so not removed
Package 'php-sabre-dav' is not installed, so not removed
Package 'php-sabre-vobject' is not installed, so not removed
Package 'php-sass' is not installed, so not removed
Package 'php-seclib' is not installed, so not removed
Package 'php-services-json' is not installed, so not removed
Package 'php-services-weather' is not installed, so not removed
Package 'php-shellcommand' is not installed, so not removed
Package 'php-smbclient' is not installed, so not removed
Package 'php-smbclient-all-dev' is not installed, so not removed
Package 'php-soap' is not installed, so not removed
Package 'php-solr' is not installed, so not removed
Package 'php-solr-all-dev' is not installed, so not removed
Package 'php-sql-formatter' is not installed, so not removed
Package 'php-ssh2' is not installed, so not removed
Package 'php-ssh2-all-dev' is not installed, so not removed
Package 'php-swiftmailer' is not installed, so not removed
Package 'php-sybase' is not installed, so not removed
Package 'php-symfony' is not installed, so not removed
Package 'php-symfony-all-my-sms-notifier' is not installed, so not removed
Package 'php-symfony-amazon-mailer' is not installed, so not removed
Package 'php-symfony-amazon-sns-notifier' is not installed, so not removed
Package 'php-symfony-amazon-sqs-messenger' is not installed, so not removed
Package 'php-symfony-amqp-messenger' is not installed, so not removed
Package 'php-symfony-asset' is not installed, so not removed
Package 'php-symfony-beanstalkd-messenger' is not installed, so not removed
Package 'php-symfony-browser-kit' is not installed, so not removed
Package 'php-symfony-cache' is not installed, so not removed
Package 'php-symfony-cache-contracts' is not installed, so not removed
Package 'php-symfony-clickatell-notifier' is not installed, so not removed
Package 'php-symfony-config' is not installed, so not removed
Package 'php-symfony-console' is not installed, so not removed
Package 'php-symfony-contracts' is not installed, so not removed
Package 'php-symfony-crowdin-translation-provider' is not installed, so not removed
Package 'php-symfony-css-selector' is not installed, so not removed
Package 'php-symfony-debug-bundle' is not installed, so not removed
Package 'php-symfony-dependency-injection' is not installed, so not removed
Package 'php-symfony-deprecation-contracts' is not installed, so not removed
Package 'php-symfony-discord-notifier' is not installed, so not removed
Package 'php-symfony-doctrine-bridge' is not installed, so not removed
Package 'php-symfony-doctrine-messenger' is not installed, so not removed
Package 'php-symfony-dom-crawler' is not installed, so not removed
Package 'php-symfony-dotenv' is not installed, so not removed
Package 'php-symfony-error-handler' is not installed, so not removed
Package 'php-symfony-esendex-notifier' is not installed, so not removed
Package 'php-symfony-event-dispatcher' is not installed, so not removed
Package 'php-symfony-event-dispatcher-contracts' is not installed, so not removed
Package 'php-symfony-expo-notifier' is not installed, so not removed
Package 'php-symfony-expression-language' is not installed, so not removed
Package 'php-symfony-fake-chat-notifier' is not installed, so not removed
Package 'php-symfony-fake-sms-notifier' is not installed, so not removed
Package 'php-symfony-filesystem' is not installed, so not removed
Package 'php-symfony-finder' is not installed, so not removed
Package 'php-symfony-firebase-notifier' is not installed, so not removed
Package 'php-symfony-form' is not installed, so not removed
Package 'php-symfony-framework-bundle' is not installed, so not removed
Package 'php-symfony-free-mobile-notifier' is not installed, so not removed
Package 'php-symfony-gateway-api-notifier' is not installed, so not removed
Package 'php-symfony-gitter-notifier' is not installed, so not removed
Package 'php-symfony-google-chat-notifier' is not installed, so not removed
Package 'php-symfony-google-mailer' is not installed, so not removed
Package 'php-symfony-http-client' is not installed, so not removed
Package 'php-symfony-http-client-contracts' is not installed, so not removed
Package 'php-symfony-http-foundation' is not installed, so not removed
Package 'php-symfony-http-kernel' is not installed, so not removed
Package 'php-symfony-inflector' is not installed, so not removed
Package 'php-symfony-infobip-notifier' is not installed, so not removed
Package 'php-symfony-intl' is not installed, so not removed
Package 'php-symfony-iqsms-notifier' is not installed, so not removed
Package 'php-symfony-ldap' is not installed, so not removed
Package 'php-symfony-light-sms-notifier' is not installed, so not removed
Package 'php-symfony-linked-in-notifier' is not installed, so not removed
Package 'php-symfony-lock' is not installed, so not removed
Package 'php-symfony-loco-translation-provider' is not installed, so not removed
Package 'php-symfony-lokalise-translation-provider' is not installed, so not removed
Package 'php-symfony-mailchimp-mailer' is not installed, so not removed
Package 'php-symfony-mailer' is not installed, so not removed
Package 'php-symfony-mailgun-mailer' is not installed, so not removed
Package 'php-symfony-mailjet-mailer' is not installed, so not removed
Package 'php-symfony-mailjet-notifier' is not installed, so not removed
Package 'php-symfony-mattermost-notifier' is not installed, so not removed
Package 'php-symfony-mercure' is not installed, so not removed
Package 'php-symfony-mercure-notifier' is not installed, so not removed
Package 'php-symfony-message-bird-notifier' is not installed, so not removed
Package 'php-symfony-message-media-notifier' is not installed, so not removed
Package 'php-symfony-messenger' is not installed, so not removed
Package 'php-symfony-microsoft-teams-notifier' is not installed, so not removed
Package 'php-symfony-mime' is not installed, so not removed
Package 'php-symfony-mobyt-notifier' is not installed, so not removed
Package 'php-symfony-monolog-bridge' is not installed, so not removed
Package 'php-symfony-nexmo-notifier' is not installed, so not removed
Package 'php-symfony-notifier' is not installed, so not removed
Package 'php-symfony-octopush-notifier' is not installed, so not removed
Package 'php-symfony-oh-my-smtp-mailer' is not installed, so not removed
Package 'php-symfony-one-signal-notifier' is not installed, so not removed
Package 'php-symfony-options-resolver' is not installed, so not removed
Package 'php-symfony-ovh-cloud-notifier' is not installed, so not removed
Package 'php-symfony-password-hasher' is not installed, so not removed
Package 'php-symfony-phpunit-bridge' is not installed, so not removed
Package 'php-symfony-polyfill' is not installed, so not removed
Package 'php-symfony-polyfill-apcu' is not installed, so not removed
Package 'php-symfony-polyfill-ctype' is not installed, so not removed
Package 'php-symfony-polyfill-iconv' is not installed, so not removed
Package 'php-symfony-polyfill-intl-grapheme' is not installed, so not removed
Package 'php-symfony-polyfill-intl-icu' is not installed, so not removed
Package 'php-symfony-polyfill-intl-idn' is not installed, so not removed
Package 'php-symfony-polyfill-intl-messageformatter' is not installed, so not removed
Package 'php-symfony-polyfill-intl-normalizer' is not installed, so not removed
Package 'php-symfony-polyfill-mbstring' is not installed, so not removed
Package 'php-symfony-polyfill-php72' is not installed, so not removed
Package 'php-symfony-polyfill-php73' is not installed, so not removed
Package 'php-symfony-polyfill-php74' is not installed, so not removed
Package 'php-symfony-polyfill-php80' is not installed, so not removed
Package 'php-symfony-polyfill-php81' is not installed, so not removed
Package 'php-symfony-polyfill-util' is not installed, so not removed
Package 'php-symfony-polyfill-uuid' is not installed, so not removed
Package 'php-symfony-polyfill-xml' is not installed, so not removed
Package 'php-symfony-postmark-mailer' is not installed, so not removed
Package 'php-symfony-process' is not installed, so not removed
Package 'php-symfony-property-access' is not installed, so not removed
Package 'php-symfony-property-info' is not installed, so not removed
Package 'php-symfony-proxy-manager-bridge' is not installed, so not removed
Package 'php-symfony-rate-limiter' is not installed, so not removed
Package 'php-symfony-redis-messenger' is not installed, so not removed
Package 'php-symfony-rocket-chat-notifier' is not installed, so not removed
Package 'php-symfony-routing' is not installed, so not removed
Package 'php-symfony-runtime' is not installed, so not removed
Package 'php-symfony-security-acl' is not installed, so not removed
Package 'php-symfony-security-bundle' is not installed, so not removed
Package 'php-symfony-security-core' is not installed, so not removed
Package 'php-symfony-security-csrf' is not installed, so not removed
Package 'php-symfony-security-guard' is not installed, so not removed
Package 'php-symfony-security-http' is not installed, so not removed
Package 'php-symfony-semaphore' is not installed, so not removed
Package 'php-symfony-sendgrid-mailer' is not installed, so not removed
Package 'php-symfony-sendinblue-mailer' is not installed, so not removed
Package 'php-symfony-sendinblue-notifier' is not installed, so not removed
Package 'php-symfony-serializer' is not installed, so not removed
Package 'php-symfony-service-contracts' is not installed, so not removed
Package 'php-symfony-sinch-notifier' is not installed, so not removed
Package 'php-symfony-slack-notifier' is not installed, so not removed
Package 'php-symfony-sms-biuras-notifier' is not installed, so not removed
Package 'php-symfony-sms77-notifier' is not installed, so not removed
Package 'php-symfony-smsapi-notifier' is not installed, so not removed
Package 'php-symfony-smsc-notifier' is not installed, so not removed
Package 'php-symfony-spot-hit-notifier' is not installed, so not removed
Package 'php-symfony-stopwatch' is not installed, so not removed
Package 'php-symfony-string' is not installed, so not removed
Package 'php-symfony-telegram-notifier' is not installed, so not removed
Package 'php-symfony-telnyx-notifier' is not installed, so not removed
Package 'php-symfony-templating' is not installed, so not removed
Package 'php-symfony-translation' is not installed, so not removed
Package 'php-symfony-translation-contracts' is not installed, so not removed
Package 'php-symfony-turbo-sms-notifier' is not installed, so not removed
Package 'php-symfony-twig-bridge' is not installed, so not removed
Package 'php-symfony-twig-bundle' is not installed, so not removed
Package 'php-symfony-twilio-notifier' is not installed, so not removed
Package 'php-symfony-uid' is not installed, so not removed
Package 'php-symfony-validator' is not installed, so not removed
Package 'php-symfony-var-dumper' is not installed, so not removed
Package 'php-symfony-var-exporter' is not installed, so not removed
Package 'php-symfony-vonage-notifier' is not installed, so not removed
Package 'php-symfony-web-link' is not installed, so not removed
Package 'php-symfony-web-profiler-bundle' is not installed, so not removed
Package 'php-symfony-workflow' is not installed, so not removed
Package 'php-symfony-yaml' is not installed, so not removed
Package 'php-symfony-yunpian-notifier' is not installed, so not removed
Package 'php-symfony-zulip-notifier' is not installed, so not removed
Package 'php-tcpdf' is not installed, so not removed
Package 'php-text-captcha' is not installed, so not removed
Package 'php-text-figlet' is not installed, so not removed
Package 'php-text-languagedetect' is not installed, so not removed
Package 'php-text-password' is not installed, so not removed
Package 'php-text-template' is not installed, so not removed
Package 'php-text-wiki' is not installed, so not removed
Package 'php-thrift' is not installed, so not removed
Package 'php-tideways' is not installed, so not removed
Package 'php-tijsverkoyen-css-to-inline-styles' is not installed, so not removed
Package 'php-timer' is not installed, so not removed
Package 'php-token-stream' is not installed, so not removed
Package 'php-tokenizer' is not installed, so not removed
Package 'php-twig' is not installed, so not removed
Package 'php-twig-cache-extra' is not installed, so not removed
Package 'php-twig-cssinliner-extra' is not installed, so not removed
Package 'php-twig-doc' is not installed, so not removed
Package 'php-twig-extra-bundle' is not installed, so not removed
Package 'php-twig-html-extra' is not installed, so not removed
Package 'php-twig-i18n-extension' is not installed, so not removed
Package 'php-twig-inky-extra' is not installed, so not removed
Package 'php-twig-intl-extra' is not installed, so not removed
Package 'php-twig-markdown-extra' is not installed, so not removed
Package 'php-twig-string-extra' is not installed, so not removed
Package 'php-uopz' is not installed, so not removed
Package 'php-uopz-all-dev' is not installed, so not removed
Package 'php-uploadprogress' is not installed, so not removed
Package 'php-uploadprogress-all-dev' is not installed, so not removed
Package 'php-uuid' is not installed, so not removed
Package 'php-uuid-all-dev' is not installed, so not removed
Package 'php-validate' is not installed, so not removed
Package 'php-vlucas-phpdotenv' is not installed, so not removed
Package 'php-webmozart-assert' is not installed, so not removed
Package 'php-wikidiff2' is not installed, so not removed
Package 'php-xajax' is not installed, so not removed
Package 'php-xdebug' is not installed, so not removed
Package 'php-xdebug-all-dev' is not installed, so not removed
Package 'php-xml-htmlsax3' is not installed, so not removed
Package 'php-xml-rpc2' is not installed, so not removed
Package 'php-xml-svg' is not installed, so not removed
Package 'php-xmlrpc' is not installed, so not removed
Package 'php-xmlrpc-all-dev' is not installed, so not removed
Package 'php-yac' is not installed, so not removed
Package 'php-yac-all-dev' is not installed, so not removed
Package 'php-yaml' is not installed, so not removed
Package 'php-yaml-all-dev' is not installed, so not removed
Package 'php-zend-code' is not installed, so not removed
Package 'php-zend-eventmanager' is not installed, so not removed
Package 'php-zend-stdlib' is not installed, so not removed
Package 'php-zeroc-ice' is not installed, so not removed
Package 'php-zeta-base' is not installed, so not removed
Package 'php-zeta-console-tools' is not installed, so not removed
Package 'php-zeta-unit-test' is not installed, so not removed
Package 'php-zip' is not installed, so not removed
Package 'php-zmq' is not installed, so not removed
Package 'php-zmq-all-dev' is not installed, so not removed
Package 'php8.1-amqp' is not installed, so not removed
Package 'php8.1-apcu' is not installed, so not removed
Package 'php8.1-ast' is not installed, so not removed
Package 'php8.1-ds' is not installed, so not removed
Package 'php8.1-gearman' is not installed, so not removed
Package 'php8.1-gmagick' is not installed, so not removed
Package 'php8.1-gnupg' is not installed, so not removed
Package 'php8.1-http' is not installed, so not removed
Package 'php8.1-igbinary' is not installed, so not removed
Package 'php8.1-imagick' is not installed, so not removed
Package 'php8.1-mailparse' is not installed, so not removed
Package 'php8.1-memcache' is not installed, so not removed
Package 'php8.1-memcached' is not installed, so not removed
Package 'php8.1-mongodb' is not installed, so not removed
Package 'php8.1-msgpack' is not installed, so not removed
Package 'php8.1-oauth' is not installed, so not removed
Package 'php8.1-pcov' is not installed, so not removed
Package 'php8.1-ps' is not installed, so not removed
Package 'php8.1-psr' is not installed, so not removed
Package 'php8.1-raphf' is not installed, so not removed
Package 'php8.1-redis' is not installed, so not removed
Package 'php8.1-rrd' is not installed, so not removed
Package 'php8.1-smbclient' is not installed, so not removed
Package 'php8.1-solr' is not installed, so not removed
Package 'php8.1-ssh2' is not installed, so not removed
Package 'php8.1-uopz' is not installed, so not removed
Package 'php8.1-uploadprogress' is not installed, so not removed
Package 'php8.1-uuid' is not installed, so not removed
Package 'php8.1-xdebug' is not installed, so not removed
Package 'php8.1-xmlrpc' is not installed, so not removed
Package 'php8.1-yac' is not installed, so not removed
Package 'php8.1-yaml' is not installed, so not removed
Package 'php8.1-zmq' is not installed, so not removed
Package 'phpab' is not installed, so not removed
Package 'phpcpd' is not installed, so not removed
Package 'phpdox' is not installed, so not removed
Package 'phpldapadmin' is not installed, so not removed
Package 'phpliteadmin' is not installed, so not removed
Package 'phpliteadmin-themes' is not installed, so not removed
Package 'phploc' is not installed, so not removed
Package 'phpmd' is not installed, so not removed
Package 'phpmyadmin' is not installed, so not removed
Package 'phppgadmin' is not installed, so not removed
Package 'phpqrcode' is not installed, so not removed
Package 'phpsysinfo' is not installed, so not removed
Package 'phpunit' is not installed, so not removed
Package 'phpunit-cli-parser' is not installed, so not removed
Package 'phpunit-code-unit' is not installed, so not removed
Package 'phpunit-code-unit-reverse-lookup' is not installed, so not removed
Package 'phpunit-comparator' is not installed, so not removed
Package 'phpunit-complexity' is not installed, so not removed
Package 'phpunit-diff' is not installed, so not removed
Package 'phpunit-environment' is not installed, so not removed
Package 'phpunit-exporter' is not installed, so not removed
Package 'phpunit-git' is not installed, so not removed
Package 'phpunit-global-state' is not installed, so not removed
Package 'phpunit-lines-of-code' is not installed, so not removed
Package 'phpunit-object-enumerator' is not installed, so not removed
Package 'phpunit-object-reflector' is not installed, so not removed
Package 'phpunit-recursion-context' is not installed, so not removed
Package 'phpunit-resource-operations' is not installed, so not removed
Package 'phpunit-type' is not installed, so not removed
Package 'phpunit-version' is not installed, so not removed
Package 'phpwebcounter' is not installed, so not removed
Package 'phpwebcounter-extra' is not installed, so not removed
Package 'php-mythtv' is not installed, so not removed
Package 'php8.1-cgi' is not installed, so not removed
Package 'php8.1-curl' is not installed, so not removed
Package 'php8.1-dev' is not installed, so not removed
Package 'php8.1-gd' is not installed, so not removed
Package 'php8.1-gmp' is not installed, so not removed
Package 'php8.1-ldap' is not installed, so not removed
Package 'php8.1-mbstring' is not installed, so not removed
Package 'php8.1-odbc' is not installed, so not removed
Package 'php8.1-pgsql' is not installed, so not removed
Package 'php8.1-pspell' is not installed, so not removed
Package 'php8.1-snmp' is not installed, so not removed
Package 'php8.1-sqlite3' is not installed, so not removed
Package 'php8.1-tidy' is not installed, so not removed
Package 'php8.1-xml' is not installed, so not removed
Package 'php8.1-bcmath' is not installed, so not removed
Package 'php8.1-bz2' is not installed, so not removed
Package 'php8.1-dba' is not installed, so not removed
Package 'php8.1-enchant' is not installed, so not removed
Package 'php8.1-fpm' is not installed, so not removed
Package 'php8.1-imap' is not installed, so not removed
Package 'php8.1-interbase' is not installed, so not removed
Package 'php8.1-intl' is not installed, so not removed
Package 'php8.1-phpdbg' is not installed, so not removed
Package 'php8.1-soap' is not installed, so not removed
Package 'php8.1-sybase' is not installed, so not removed
Package 'php8.1-xsl' is not installed, so not removed
Package 'php8.1-zip' is not installed, so not removed
The following packages will be REMOVED:
  libapache2-mod-php* libapache2-mod-php8.1* php* php-common* php-mysql* php8.1* php8.1-cli* php8.1-common* php8.1-mysql* php8.1-opcache*
  php8.1-readline*
0 upgraded, 0 newly installed, 11 to remove and 1 not upgraded.
After this operation, 21.8 MB disk space will be freed.
Do you want to continue? [Y/n] Y
(Reading database ... 65124 files and directories currently installed.)
Removing libapache2-mod-php (2:8.1+92ubuntu1) ...
Removing php (2:8.1+92ubuntu1) ...
Removing php8.1 (8.1.2-1ubuntu2.10) ...
Removing libapache2-mod-php8.1 (8.1.2-1ubuntu2.10) ...
Module php8.1 disabled.
apache2_invoke prerm: Disable module php8.1
apache2_reload: Your configuration is broken. Not restarting Apache 2
apache2_reload: apache2: Syntax error on line 147 of /etc/apache2/apache2.conf: Syntax error on line 6 of /etc/apache2/mods-enabled/dir.conf: </IfModule><IfModule without matching <IfModule><IfModule section
Removing php8.1-cli (8.1.2-1ubuntu2.10) ...
Removing php8.1-readline (8.1.2-1ubuntu2.10) ...
Removing php8.1-opcache (8.1.2-1ubuntu2.10) ...
Removing php-mysql (2:8.1+92ubuntu1) ...
Removing php8.1-mysql (8.1.2-1ubuntu2.10) ...
Removing php8.1-common (8.1.2-1ubuntu2.10) ...
Removing php-common (2:92ubuntu1) ...
Warning: Stopping phpsessionclean.service, but it can still be activated by:
  phpsessionclean.timer
Processing triggers for man-db (2.10.2-1) ...
(Reading database ... 64985 files and directories currently installed.)
Purging configuration files for php-common (2:92ubuntu1) ...
Purging configuration files for php8.1-common (8.1.2-1ubuntu2.10) ...
dpkg: warning: while removing php8.1-common, directory '/etc/php/8.1/mods-available' not empty so not removed
Purging configuration files for php8.1-mysql (8.1.2-1ubuntu2.10) ...
Purging configuration files for php8.1-cli (8.1.2-1ubuntu2.10) ...
Purging configuration files for php8.1-readline (8.1.2-1ubuntu2.10) ...
Purging configuration files for libapache2-mod-php8.1 (8.1.2-1ubuntu2.10) ...
apache2_invoke postrm: Purging state for php8.1
dpkg: warning: while removing libapache2-mod-php8.1, directory '/etc/php/8.1' not empty so not removed
Purging configuration files for php8.1-opcache (8.1.2-1ubuntu2.10) ...
ubuntu@ip-172-31-11-176:~$ sudo mkdir /var/www/projectlamp
mkdir: cannot create directory ‘/var/www/projectlamp’: File exists
ubuntu@ip-172-31-11-176:~$ sudo vim /etc/apache2/mods-enabled/dir.conf
ubuntu@ip-172-31-11-176:~$ sudo systemctl reload apache2
ubuntu@ip-172-31-11-176:~$ vim /var/www/projectlamp/index.php
ubuntu@ip-172-31-11-176:~$ ubuntu@ip-172-31-11-176:~$ sudo apt install php libapache2-mod-php php-mysql
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libapache2-mod-php8.1 php-common php8.1 php8.1-cli php8.1-common php8.1-mysql php8.1-opcache php8.1-readline
Suggested packages:
  php-pear
The following NEW packages will be installed:
  libapache2-mod-php libapache2-mod-php8.1 php php-common php-mysql php8.1 php8.1-cli php8.1-common php8.1-mysql php8.1-opcache php8.1-readline
0 upgraded, 11 newly installed, 0 to remove and 1 not upgraded.
Need to get 5264 kB of archives.
After this operation, 21.8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 php-common all 2:92ubuntu1 [12.4 kB]
Get:2 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-common amd64 8.1.2-1ubuntu2.10 [1126 kB]
Get:3 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-opcache amd64 8.1.2-1ubuntu2.10 [365 kB]
Get:4 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-readline amd64 8.1.2-1ubuntu2.10 [13.6 kB]
Get:5 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-cli amd64 8.1.2-1ubuntu2.10 [1833 kB]
Get:6 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 libapache2-mod-php8.1 amd64 8.1.2-1ubuntu2.10 [1767 kB]
Get:7 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 libapache2-mod-php all 2:8.1+92ubuntu1 [2898 B]
Get:8 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1 all 8.1.2-1ubuntu2.10 [9156 B]
Get:9 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 php all 2:8.1+92ubuntu1 [2756 B]
Get:10 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-mysql amd64 8.1.2-1ubuntu2.10 [130 kB]
Get:11 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 php-mysql all 2:8.1+92ubuntu1 [1834 B]
Fetched 5264 kB in 0s (28.7 MB/s)
Selecting previously unselected package php-common.
(Reading database ... 64976 files and directories currently installed.)
Preparing to unpack .../00-php-common_2%3a92ubuntu1_all.deb ...
Unpacking php-common (2:92ubuntu1) ...
Selecting previously unselected package php8.1-common.
Preparing to unpack .../01-php8.1-common_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking php8.1-common (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package php8.1-opcache.
Preparing to unpack .../02-php8.1-opcache_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking php8.1-opcache (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package php8.1-readline.
Preparing to unpack .../03-php8.1-readline_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking php8.1-readline (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package php8.1-cli.
Preparing to unpack .../04-php8.1-cli_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking php8.1-cli (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package libapache2-mod-php8.1.
Preparing to unpack .../05-libapache2-mod-php8.1_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking libapache2-mod-php8.1 (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package libapache2-mod-php.
Preparing to unpack .../06-libapache2-mod-php_2%3a8.1+92ubuntu1_all.deb ...
Unpacking libapache2-mod-php (2:8.1+92ubuntu1) ...
Selecting previously unselected package php8.1.
Preparing to unpack .../07-php8.1_8.1.2-1ubuntu2.10_all.deb ...
Unpacking php8.1 (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package php.
Preparing to unpack .../08-php_2%3a8.1+92ubuntu1_all.deb ...
Unpacking php (2:8.1+92ubuntu1) ...
Selecting previously unselected package php8.1-mysql.
Preparing to unpack .../09-php8.1-mysql_8.1.2-1ubuntu2.10_amd64.deb ...
Unpacking php8.1-mysql (8.1.2-1ubuntu2.10) ...
Selecting previously unselected package php-mysql.
Preparing to unpack .../10-php-mysql_2%3a8.1+92ubuntu1_all.deb ...
Unpacking php-mysql (2:8.1+92ubuntu1) ...
Setting up php-common (2:92ubuntu1) ...
Created symlink /etc/systemd/system/timers.target.wants/phpsessionclean.timer → /lib/systemd/system/phpsessionclean.timer.
Setting up php8.1-common (8.1.2-1ubuntu2.10) ...

Creating config file /etc/php/8.1/mods-available/calendar.ini with new version

Creating config file /etc/php/8.1/mods-available/ctype.ini with new version

Creating config file /etc/php/8.1/mods-available/exif.ini with new version

Creating config file /etc/php/8.1/mods-available/fileinfo.ini with new version

Creating config file /etc/php/8.1/mods-available/ffi.ini with new version

Creating config file /etc/php/8.1/mods-available/ftp.ini with new version

Creating config file /etc/php/8.1/mods-available/gettext.ini with new version

Creating config file /etc/php/8.1/mods-available/iconv.ini with new version

Creating config file /etc/php/8.1/mods-available/pdo.ini with new version

Creating config file /etc/php/8.1/mods-available/phar.ini with new version

Creating config file /etc/php/8.1/mods-available/posix.ini with new version

Creating config file /etc/php/8.1/mods-available/shmop.ini with new version

Creating config file /etc/php/8.1/mods-available/sockets.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvmsg.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvsem.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvshm.ini with new version

Creating config file /etc/php/8.1/mods-available/tokenizer.ini with new version
Setting up php8.1-mysql (8.1.2-1ubuntu2.10) ...

Creating config file /etc/php/8.1/mods-available/mysqlnd.ini with new version

Creating config file /etc/php/8.1/mods-available/mysqli.ini with new version

Creating config file /etc/php/8.1/mods-available/pdo_mysql.ini with new version
Setting up php8.1-readline (8.1.2-1ubuntu2.10) ...

Creating config file /etc/php/8.1/mods-available/readline.ini with new version
Setting up php8.1-opcache (8.1.2-1ubuntu2.10) ...

Creating config file /etc/php/8.1/mods-available/opcache.ini with new version
Setting up php-mysql (2:8.1+92ubuntu1) ...
Setting up php8.1-cli (8.1.2-1ubuntu2.10) ...
update-alternatives: using /usr/bin/php8.1 to provide /usr/bin/php (php) in auto mode
update-alternatives: using /usr/bin/phar8.1 to provide /usr/bin/phar (phar) in auto mode
update-alternatives: using /usr/bin/phar.phar8.1 to provide /usr/bin/phar.phar (phar.phar) in auto mode

Creating config file /etc/php/8.1/cli/php.ini with new version
Setting up libapache2-mod-php8.1 (8.1.2-1ubuntu2.10) ...

Creating config file /etc/php/8.1/apache2/php.ini with new version
apache2_invoke: Enable module php8.1
Setting up php8.1 (8.1.2-1ubuntu2.10) ...
Setting up libapache2-mod-php (2:8.1+92ubuntu1) ...
Setting up php (2:8.1+92ubuntu1) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for php8.1-cli (8.1.2-1ubuntu2.10) ...
Processing triggers for libapache2-mod-php8.1 (8.1.2-1ubuntu2.10) ...
Scanning processes...
Scanning linux images...

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-11-176:~$ php -v
PHP 8.1.2-1ubuntu2.10 (cli) (built: Jan 16 2023 15:19:49) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.2, Copyright (c) Zend Technologies
    with Zend OPcache v8.1.2-1ubuntu2.10, Copyright (c), by Zend Technologies
ubuntu@ip-172-31-11-176:~$ vim /var/www/projectlamp/index.php
