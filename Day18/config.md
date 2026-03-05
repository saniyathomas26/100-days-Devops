
# Commands Executed

## For all app servers (stapp01,stapp02,stapp03)

sudo yum install httpd php php-mysqlnd php-fpm -y

sudo sed -i 's/Listen 80/Listen 6000/' /etc/httpd/conf/httpd.conf

sudo systemctl start httpd

sudo systemctl enable httpd

sudo systemctl restart httpd

## On DB server (stdb01)
sudo yum install mariadb-server -y

sudo systemctl start mariadb

sudo systemctl enable mariadb

mysql -u root or mysql 

CREATE DATABASE kodekloud_db5;
CREATE USER 'kodekloud_top'@'%' IDENTIFIED BY ''Rc5C9EyvbU';
GRANT ALL PRIVILEGES ON kodekloud_db5.* TO 'kodekloud_top'@'%';
FLUSH PRIVILEGES;
EXIT;
