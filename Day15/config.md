# Commands Executed

## Connect to App Server
ssh banner@stapp02

## Install and Start Nginx
sudo yum install -y nginx


sudo systemctl enable nginx


sudo systemctl start nginx


sudo systemctl status nginx
## Create index.html
cat > /usr/share/nginx/html/index.html

Welcome!
## Configure SSL in nginx

cd /etc/nginx


vi nginx.conf and copy the following


 Settings for a TLS enabled server.

    server {
        listen       443 ssl http2;
        listen       [::]:443 ssl http2;
        server_name  _;
        root         /usr/share/nginx/html;

        ssl_certificate "/etc/pki/nginx/server.crt";
        ssl_certificate_key "/etc/pki/nginx/private/server.key";

## Create Certificates Directory

mkdir certs


cd certs
## Copy SSL certificate and key
cp /tmp/nautilus.crt server.crt


cp /tmp/nautilus.key server.key

## Modify copied text from nginx
ssl_certificate "/etc/nginx/server.crt";


ssl_certificate_key "/etc/nginx/private/server.key";

## Modify the nginx.config
cd ..

vi nginx.conf


Add the server details modified ssl certifcate and key

## Test Configuration
nginx -t

## Restart Nginx
systemctl restart nginx
## Try curl
curl https://stapp01


curl http://stapp01
