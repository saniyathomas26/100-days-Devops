# Command Executed

curl stapp01:5003

## Connect to App Server 1

ssh tony@stapp01



sudo su

## Check Apache Service Status

systemctl status httpd -l

## Verify Port Usage

netstat -tunlp | grep 3004

## Modify Sendmail Configuration

vi /etc/mail/sendmail.cf



 Update port from 3004 to 3005

## Restart Services

systemctl restart sendmail



systemctl restart httpd

## Verification

curl stapp01:3005
