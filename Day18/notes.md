
 # Day18 - Configure LAMP server

# Task:

Deploy a WordPress-ready application stack for xFusionCorp Industries in Stratos Datacenter.

On all App Hosts:

Install httpd, php, and required PHP dependencies.

Configure Apache to listen on port 6000.

Start and enable httpd.

Ensure shared storage /vaw/www/html is mounted at /var/www/html.

On DB Server:

Install and configure MariaDB server.

Create database kodekloud_db1.

Create user kodekloud_roy with password LQfKeWWxWD.

Grant all privileges on kodekloud_db1 to kodekloud_roy.

Validate:

Access the application using the LBR link (App button).

Confirm the message:
“App is able to connect to the database using user kodekloud_roy”

# Purpose:

To configure a high-availability web application stack with shared storage, a load-balanced Apache service running on port 6000, and a properly secured MariaDB backend.

This ensures successful application-to-database connectivity and validates that the infrastructure is ready to serve traffic in the Stratos Datacenter environment.
