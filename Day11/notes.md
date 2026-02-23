# Day 11 – Deploying ROOT.war on Tomcat (Port 6300)
Objective

Install Tomcat on App Server 3 (stapp03), configure it to run on port 6300, deploy the ROOT.war file from Jump Host, and verify the application works using the base URL.

## Part 1 – Steps Performed on Jump Host

The ROOT.war file was available on the Jump Host at /tmp. The first step was to transfer this file to App Server 3.

- scp /tmp/ROOT.war banner@stapp03:/home/banner/

After entering the password, the file was successfully copied to /home/banner/ on stapp03.

To verify the deployment after configuration, the following command was executed from the Jump Host:

- curl http://stapp03:6300

Once everything was configured correctly, this returned:

Welcome to xFusionCorp Industries!

## Part 2 – Steps Performed on App Server 3 (stapp03)

First, login to App Server 3:

- ssh banner@stapp03

Install Tomcat:

- sudo yum install -y tomcat

Next, configure Tomcat to run on port 6300 instead of the default 8080 by editing the configuration file:

- sudo vi /etc/tomcat/server.xml

Inside the file, locate the Connector configuration:

<Connector port="8080" protocol="HTTP/1.1"

Change the port to 6300:

- <Connector port="6300" protocol="HTTP/1.1"

Save the file and restart Tomcat:

- sudo systemctl restart tomcat

Verify Tomcat service status:

- sudo systemctl status tomcat

Now deploy the application by moving the ROOT.war file to the Tomcat webapps directory:

- sudo mv /home/banner/ROOT.war /usr/share/tomcat/webapps/

Restart Tomcat again to deploy the application:

- sudo systemctl restart tomcat
