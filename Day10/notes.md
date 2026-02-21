# xFusionCorp Beta Website Backup Script Notes

The production support team at xFusionCorp Industries is automating daily tasks using bash scripts. One task is creating a backup for a static website running on App Server 2 in the Stratos Datacenter. The goal is to have a bash script named beta_backup.sh that creates a backup of /var/www/html/beta, saves it locally in /backup/ on App Server 2, and copies it to the Nautilus Backup Server without asking for a password.

First, log in to App Server 2 as steve using SSH:
ssh steve@stapp02
# Confirm host authenticity with yes and enter password if prompted.

Navigate to the scripts directory:
cd /scripts/
ls -l

Create the backup script using cat:
cat > beta_backup.sh
# Paste the following script content:

#!/bin/bash
# Create a zip archive of the beta website
zip /backup/xfusioncorp_beta.zip /var/www/html/beta
# Copy the backup to Nautilus Backup Server
scp /backup/xfusioncorp_beta.zip clint@stbkp01:/backup/

# Save and exit cat (Ctrl+C if using cat).

Make the script executable:
chmod +x beta_backup.sh
ls -l
# Verify permissions: -rwxr-xr-x

Install the zip package if not already installed:
sudo yum install zip

Generate an SSH key pair for passwordless login:
ssh-keygen -t rsa

#Press Enter to accept default location /home/steve/.ssh/id_rsa

#Press Enter to skip passphrase if desired.

#Overwrite existing key if prompted.

Copy the public key to Nautilus Backup Server:
ssh-copy-id clint@stbkp01
# Confirm host authenticity with yes and enter password for clint.

Test passwordless SSH login:
ssh clint@stbkp01
cd /backup/
ls -l
exit

Run the backup script:
./beta_backup.sh

Verify the backup file locally and on Nautilus Backup Server:
ls -l /backup/
ssh clint@stbkp01
cd /backup/
ls -l
exit

This script ensures that /var/www/html/beta is archived as xfusioncorp_beta.zip, saved in /backup/ on App Server 2, and copied to /backup/ on Nautilus Backup Server automatically without requiring a password. The /backup/ directory on App Server 2 is temporary storage and is cleaned weekly. The script does not use sudo and can be executed by authorized users.

