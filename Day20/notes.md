
# Day20 - Configure Nginx + PHP-FPM Using Unix Sock 

# Task:

Configure App Server 2 (stapp02) to deploy a PHP-based application:

Install nginx and configure it to:

Listen on port 8094

Use document root: /var/www/html

Set index index.php index.html;

Install PHP-FPM 8.2 and configure it to:

Use Unix socket: /var/run/php-fpm/default.sock

Create parent directories if missing

Ensure proper permissions for nginx access

Configure nginx to pass PHP requests via:

fastcgi_pass /var/run/php-fpm/default.sock

Include fastcgi_params

Set fastcgi_index index.php

Enable and start both services.



## Purpose:

Provision nginx + PHP-FPM 8.2 using Unix socket-based FastCGI to serve the PHP application on port 8094 and verify successful integration via curl.

