## Day15 - Configure LBR Server for High Availability Load Balancing
# Task:
Install nginx on the LBR (Load Balancer) server and configure HTTP load balancing using all available App Servers by modifying only the main Nginx configuration file located at:

/etc/nginx/nginx.conf


Within the http context:

Define an upstream block including all App Servers with their existing Apache ports (do not modify Apache port configurations on backend servers).

Configure a server block listening on port 80.

Add a location / block with proxy_pass pointing to the defined upstream group.

Ensure Apache service is up and running on all App Servers without altering their existing port configurations.

After completing the configuration, validate nginx syntax, restart the nginx service, and verify accessibility of the application using the StaticApp button from the top bar.

# Purpose:
To implement a High Availability (HA) architecture on Nautilus infrastructure in Stratos DC by configuring nginx as a reverse proxy load balancer in front of multiple Apache backend servers. This setup distributes incoming traffic across all App Servers, improves performance under increasing traffic load, eliminates single-point-of-failure risk, and ensures reliable access to the application through the Load Balancer endpoint.
