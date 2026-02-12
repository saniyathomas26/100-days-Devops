
# Command Executed

## Connect to App Server 3
ssh banner@stapp03


## Switch to root user
sudo su -


## Install SELinux packages
yum install -y selinux*
yum install -y selinux* --nobest

## Navigate to SELinux configuration directory
cd /etc/selinux


## Edit SELinux configuration file
vi config


## Update SELinux mode
SELINUX=disabled

# Verification
## Verify SELinux configuration file
cat /etc/selinux/config | grep SELINUX

# Output
## SELINUX=disabled
