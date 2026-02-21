# xFusionCorp Beta Website Backup Configuration File

# Source website directory to backup
SOURCE_DIR=/var/www/html/beta

# Local backup directory on App Server 2
LOCAL_BACKUP_DIR=/backup

# Backup file name
BACKUP_FILE=xfusioncorp_beta.zip

# Nautilus Backup Server details
BACKUP_USER=clint
BACKUP_HOST=stbkp01
BACKUP_DIR=/backup

# SSH key for passwordless copy (optional, default location)
SSH_KEY=/home/steve/.ssh/id_rsa

# Log file (optional)
LOG_FILE=/var/log/beta_backup.log
