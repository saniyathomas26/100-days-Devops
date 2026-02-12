
# Command Executed

## Connect to App Server 3  
ssh banner@stapp03

## Switch to root user  
sudo su -

## Navigate to script location  
cd /tmp

## Grant executable permission to all users  
chmod 755 xfusioncorp.sh
OR
chmod +xr xfusioncorp.sh

# Verification  
Check file permissions  
ls -l xfusioncorp.sh

# Output  
-r-xr-xr-x 1 root root xfusioncorp.sh
