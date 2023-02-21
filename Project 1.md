# WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
Everything you will be doing as a DevOps engineer is around software, websites, applications etc. And, there are different stack of technologies that make different solutions possible. These stack of technologies are regarded as WEB STACKS. Examples of Web Stacks include LAMP, LEMP, MEAN, and MERN stacks. As you proceed in your journey, you will be required to understand and implement all of these technology stacks.

## What is a Technology stack?
A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. Below are the list of the Technology Stack

LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)
LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
MEAN (MongoDB, ExpressJS, AngularJS, NodeJS

## STEP 1 — INSTALLING APACHE AND UPDATING THE FIREWALL
What exactly is Apache? Apache HTTP Server is the most widely used web server software. Developed and maintained by Apache Software Foundation, Apache is an open source software available for free. It runs on 67% of all webservers in the world. It is fast, reliable, and secure. Websites and other applications can run on other web server software as well. Such as Nginx, Microsoft’s IIS, etc

The Apache web server is among the most popular web servers in the world, this makes it a great default choice for hosting a website.

So we proceed to Install Apache using Ubuntu’s package manager ‘apt’:

### update a list of packages in package manager
sudo apt update

### run apache2 package installation
sudo apt install apache2

### To verify that apache2 is running as a Service in our OS, use following command
sudo systemctl status apache2

If it is green and running, then you did everything correctly – you have just launched your first Web Server in the Clouds!

**Picture Confirmation that apache2 is running**
![PBL1_1](https://user-images.githubusercontent.com/122687798/220348408-8f32d8ef-fcd1-49a0-8edc-8eb8a56dfe67.JPG)

Before we can receive any traffic by our Web Server which is now running on apache2, we need to open TCP port 80 which is the default port that web browsers use to access web pages on the Internet. So to do this, we allow inbound traffic on port 80 on the EC2 instance

Our server is running and we can access it locally and from the Internet (Source 0.0.0.0/0 means ‘from any IP address’). First, let us try to check how we can access it locally in our Ubuntu shell, run:

 curl http://localhost:80
or
 curl http://127.0.0.1:80
 
These 2 commands above actually do pretty much the same – they use ‘curl’ command to request our Apache HTTP Server on port 80 (actually you can even try to not specify any port – it will work anyway). The difference is that: in the first case we try to access our server via DNS name and in the second one – by IP address (in this case IP address 127.0.0.1 corresponds to DNS name ‘localhost’ and the process of converting a DNS name to IP address is called "resolution")

As an output I can see some strangely formatted test, see below, so i just made sure that our Apache web service responds to ‘curl’ command with some payload.

**Picture Confirmation that CURL command was OK**
![PBL1_2](https://user-images.githubusercontent.com/122687798/220352781-57eb8428-76e0-428c-af59-10d935d45a4e.JPG)

Now it is time for us to test how our Apache HTTP server can respond to requests from the Internet. Open a web browser of your choice and try to access following url

http://<Public-IP-Address>:80....so we go
http://100.25.118.204:80  
  
**Picture Confirmation that CURL command was OK**   
![PBL1_3](https://user-images.githubusercontent.com/122687798/220354707-aa79e13e-7639-43c3-b69d-5a6c8d94b65f.JPG)
  
NBAnother way to retrieve your Public IP address, other than to check it in AWS Web console, is to use following command:
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
