
# Commands Executed

## Connect to LBR server
ssh loki@stlb01

sudo su
## Install and start nginx
yum install-y nginx
systemctl start nginx

## Connect to stapp01 in Terminal 02
ssh tony@stapp01

## Get the port details from httpd.conf file
/etc/httpd/conf/httpd.conf

Value:3000

## Navigate to Terminal 1 and LBR server
vi /etc/nginx/nginx.conf

## Add the following in conf file

 upstream app_servers {
     server stapp01:3000;
     server stapp02:3000;
     server stapp03:3000;
     }
        location / {
        proxy_pass http://app_servers;
        }

## Verifying if changes are looking good
nginx -t

## Restart nginx
systemctl restart nginx

# Verification
curl localhost:3000
