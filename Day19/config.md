
## Commands Executed
# Connect to app server 01
ssh tony@stapp01

sudo su

## Install Apache 
yum install httpd -y

## Update port details and start the service

sed -i 's/Listen 80/Listen 3003/' /etc/httpd/conf/httpd.conf

systemctl start httpd

## Connect to jumhost server
scp -r apps tony@stapp01:home/tony/

scp -r ecommerce tony@stapp01:home/tony/

## Move the files to differenr folder in stapp01
mv * /var/www/html

cd /var/www/htnl/

ls

# Verification
curl -L http://stapp01:3003/apps
curl -L http://stapp01:3003/ecommerce
