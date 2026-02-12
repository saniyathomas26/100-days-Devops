
# Command Executed

## Connect to App Server 1, App Server 2, App Server 3
ssh banner@stapp01

## Switch to root user
sudo su -

## Install cronie package
yum install -y cronie

## Start and enable crond service
systemctl start crond
systemctl enable crond

## Add cron job for root user
crontab -e

## Cron entry added
*/5 * * * * echo hello > /tmp/cron_text

# Verification
Check crond service status
systemctl status crond

# List root cron jobs
crontab -l
