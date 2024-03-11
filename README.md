# PROJECT-LAMP-stack

A “LAMP” stack is a group of open source software that is typically installed together in order to enable a server to host dynamic websites and web apps written in PHP. This term is an acronym which represents the 'LINUX' operating system with the 'APACHE' web server. The site data is stored in a 'MySQL' database, and dynamic content is processed by 'PHP'.

Part 1: Setting Up LAMP Stack

1.ON YOUR AWS CONSOLE Launch EC2 Instance:
Deploy an EC2 instance with Ubuntu Linux OS, ensuring correct configurations.
after launching your instance, remember to edit the inbound rules of your ec2 instance 
to create a new inbound rule set to http and IPv4 : cidir block 0.0.0.0/0
 

2.
i. ON YOUR COMMAND PROMPT Connect to Instance:
Establish SSH connection to the EC2 instance.
cd "path to your key file" for eg- cd C:\Users\NAME\linux key  (remember to put the cd command before the path)
then, click enter and copy and paste your AWS CONSOLE SSH (its found when you click on your instance name and click on connect, 
under the 'connect to instance' page click on the SSH client and you will find your instance public DNS that
looks like this ssh -i /path/to/your/private-key.pem ec2-user@your-ec2-public-ip
                   
                                OR

ii. TO CONNECT to your instance VIA YOUR AWS LINUX (UBUNTU) - 
ON YOUR AWS CONSOLE click on your instance name and cick on 'connect',
on the connect to instance page under 'Connect using EC2 Instance Connect, get to the end and click on connect.


update to the latest version by running the command - 

sudo apt update


3.Install Components:
Install Apache, MySQL, and PHP packages using package manager commands--

sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql


4.Start Services:
Initiate Apache and MySQL services to ensure functionality 
run these commands -

sudo systemctl start apache2

sudo systemctl start mysql

sudo systemctl status apache2

sudo systemctl status mysql

echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php  (i did this one on AWS LINUX)

php -v


5.Test LAMP Stack:
Create and access a PHP info file to verify stack operation.

go to your AWS CONSOLE and copy your public IP address (it shows when you click on your instance)
then paste it on your browser http://your public IP address  
-this will show an image of UBUNTU's apache default page.
This is the default welcome page used to test the correct operation of the Apache2 server after installation on Ubuntu systems.

then paste this on your browser http://your public IP address/info.php 
this show vital info about the php program you istalled.


notes -

after launching your instance, remember to edit the inbound rules of your ec2 instance 
to create a new inbound rule set to http and IPv4 : cidir block 0.0.0.0/0
 
on your command prompt or AWS Linux run the following commands -

sudo apt update

sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql

sudo systemctl start apache2

sudo systemctl start mysql

sudo systemctl status apache2

sudo systemctl status mysql

echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php

php -v

http://your public IP address

http://your public IP address/info.php


if you encounter any errors which you are unable to resolve its best you terminate the instance
 and start afresh by launching a new instance and redoing the whole process again

find my screenshots to help make all this info clearer
thank you.

