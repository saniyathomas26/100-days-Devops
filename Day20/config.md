
# Commands Executed

## Connect to App server 02
ssh tony@stapp02

sudo su

## Install nginx
yum install -y nginx

## Updating port and document root
vi /etc/nginx/nginx.conf 

systemctl start nginx

## Checking centos version
cat /etc/*release*

## Commands for installing php-fpm version 8.2
sudo dnf install https://rpms.remirepo.net/enterprise/remi-release-9.rpm

sudo dnf module reset php

sudo dnf module enable php:remi-8.2

sudo dnf install php-cli php-fpm php-mbstring php-xml php-mysqlnd

## Check php version

php -v

## Updating php-fpm config file with unix socket
vi /etc/php-fpm.d/www.conf

## Verifying and Restarting nginx
nginx -t

systemctl start nginx

# Verification
curl localhost:8094

# Output 
Welcome to xFusionCorp Industries!
