# PBL-Project1

## LAMP STACK IMPLEMENTATION

We are setting up a LAMP STACK using EC2, to do this we need to do the following:

- create an account on AWS.
- we create an instance (virtual machine) by selecting “ubuntu server 20.04 LTS” from Amazon Machine Image(AMI)(free tier).
- we select “t2.micro(free tier eligible)”
- Then go to the security group and select “a security group” review and launch.

We 1st create an aws free tier account, and then launch into the instance as shown in the screenshot:  

![pj1](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/3a3ebee3-82bc-4618-bf06-045dcf99b79e)

We connect to the instance from our ubuntu terminal using the command:

`ssh -i onoky project1-ec2.pem ubuntu@44.210.117.5`

![pj2](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/456bc648-71e2-47c2-9030-2a620f38c953)

## APACHE WEB SERVER SETUP

To install the Apache web server, we first update the software packages in the software package manager by running the command:

`sudo apt update`

![pj3](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/15f4f3b8-0731-43fd-80c0-190859d08a79)

Next we install the web server(Apache HTTP server) by running the command:

`sudo apt install apache2`

![pj4](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/90971fbb-f047-4770-83f4-19b5b41e9556)

To check if the webserver is running, we use the command:

`sudo systemctl status apache2`

![pj5](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/76a7413b-28cd-41fb-95a4-afd006075f00)

We then go to our instance and set the inbound rules and save

![pj6](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/aa5b61a1-ce73-4ed5-be0b-1a79caa54f55)

We copy the URL and paste on a web browser to check if it is working:

![pj7](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/f153c8bd-44a1-4abb-bb7e-7821781def9b)


## MYSQL DATABASE SERVER SET UP

We install the Mysql server by running the command:

`sudo apt install mysql-server`

![pj8](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/61f6412f-1424-4d30-ba9e-2385da9bea4c)

We log into the mysql by running the command:

`sudo mysql`

![pj9](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/ffa9475c-3965-4cc2-aae6-0d740e28b91c)

To set password as "PassWord.1" for root user, we run the command:

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

![pj10](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/a3359726-a745-4b91-a48e-b3a846189dd3)

Then we “exit” the mysql and then run the command to start the interactive script:

`sudo mysql_secure_installation`

![pj11](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/bf23a5b3-f6d2-458c-9ade-52977e3cece0)
![pj12](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/26e78779-3184-4e5c-8783-f458c74539d0)

Logged into mysql using my new password by running the command:

`sudo mysql -p`

![pj13](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/360445d9-0c87-46c9-beea-8322022b3a17)

Then “exit”.

## SETTING UP PHP

To install PHP, we run the command:

`sudo apt install php libapache2-mod-php php-mysql`

We check the version by running the command:

`php -v`

![pj14](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/fab550e6-83b9-4396-9a75-fb9177573124)

## CREATING A VIRTUAL HOST FOR APACHE

To create a virtual host for my website files using apache, we create a directory “projectlamp” Then change ownership :

`sudo mkdir /var/www/projectlamp`

`sudo chown -R $USER:$USER /var/www/projectlamp`

![pj15](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/318d0bcd-f559-4e47-83d4-f22ae7d988b7)

Created a new configuration file by running the command:

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

We place the following in the file we created

```
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

![pj16](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/93268eef-b7e8-4f41-814a-c1c15050d42c)

We save using ":wq" + "Enter"

We enable the new virtual host

`sudo a2ensite projectlamp`

We disable the default website that comes with apache.

`sudo a2dissite 000-default`

To make sure our configuration files does not contain syntax error:

`sudo apache2ctl configtest`

We reload the apache webserver

`sudo systemctl reload apache2`

We create a file in /var/www/projectlamp named “index.html”

`touch /var/www/projectlamp/index.html`

We then redirecting these data into the file:

`echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

![pj17](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/a27d2487-f3c2-41d3-9986-b6664d92b3ee)

we can check on the browser using the url

`http://<Public-IP-Address>:80`

![pj18](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/b0f581c8-0686-4cf6-99be-c42391a34642)

To enable PHP on the website, we open this file and edit it:

`sudo vim /etc/apache2/mods-enabled/dir.conf`

![pj19](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/c9a6a460-5d05-47ca-8090-ab366ac30e0f)

we use ":wq" + "Enter" to save.

Create and open another file in “projectlamp” named “index.php”

`vim /var/www/projectlamp/index.php`

Add this to the file

```
<?php
phpinfo();
```
![pj20](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/b9864fd9-97cc-4327-8bd6-7407ce3a032f)

“Save” the file, then go to the browser to refresh


![pj21](https://github.com/EzeOnoky/Project-Base-Learning-1/assets/122687798/d1a69da4-60b4-43bc-9643-b5c1496374b9)

We remove the “index.php” file created in “projectlamp:

`sudo rm /var/www/projectlamp/index.php`


# CONGRATULATIONS EZE ...you have successfully deployed a LAMP STACK WEBSITE on AWS CLOUD !!!






