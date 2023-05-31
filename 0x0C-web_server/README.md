0x0C WEB SERVER
TASK 1.
STEP 1. THIS TASK MUST BE DONE ON YOUR SERVER
FIRST LOGIN TO YOUR SERVER

HOW TO CONNECT TO YOUR WEB-01 SERVER
1. PLEASE OPEN YOUR (UBUNTU 20.04 LTS) SANDBOX AND RUN THE FOLLOWING COMMANDS

	cd /root
  	ls -a
	cd .ssh
	ls
	
2. //create a shell environment variable that contains information about the new agent instance
	
  eval $('ssh-agent')

3.//add the private key file for the "school" SSH key pair to the ssh-agent.	

  ssh-add ~/.ssh/school

PLEASE NOTE:
4. In the next command, REPLACE 18.234.168.34 with YOUR OWN IP ADDRESS 
//connect with your server

  ssh ubuntu@18.234.168.34

IF YOU HAVE CONNECTED SUCCESSFULLY you should see something like this:
ubuntu@web-01-server:~$

NOW,You can begin the tasks in the project
    
STEP 2: HOW TO INSTALL NGINX ON A WEB SERVER
//Now that you are in your server, Here are the steps to install nginx on a web server:

# Update the package index:
sudo apt update

//This will update the package index on your server and ensure that you can install the latest version of nginx.

# Install nginx:

sudo apt install nginx

//This command will install nginx on your server.

# Verify that nginx is running:

sudo service nginx status

//This command will display the status of nginx. If nginx is running,
you should see a message indicating that it is active.

# Configure the firewall:
If you have a firewall enabled on your server, you will need to allow traffic on port 80 (HTTP) and 443 (HTTPS) 
so that nginx can serve web pages. For example, if you are using UFW as your firewall, 
you can allow traffic on these ports with the following commands:

sudo ufw allow 'Nginx Full'

//This will allow incoming HTTP and HTTPS traffic to your server.

# Test nginx:
Open a web browser and enter your server's IP address or domain name.
You should see the default nginx welcome page, indicating that nginx is installed and working properly.

That's it! You now have nginx installed on your web server and are ready to start serving web pages.


CONTENT FOR YOUR 1-install_nginx_web_server FILE
DON'T FORGET TO MAKE IT EXECUTABLE BY USING chmod u+x

#!/usr/bin/env bash
# Installs nginx server on an ubuntu linux distro.

sudo apt-get update
sudo apt-get -y install nginx

# Open firewall port 80 (HTTP) for Nginx
sudo ufw allow 'Nginx HTTP'

# Configure Nginx to serve Hello World page
sudo sh -c 'echo "Hello World!" > /var/www/html/index.html'

# Start Nginx service
sudo service nginx start
