# Command Executed

## Connect to App Server 1
ssh banner@stapp01

## Switch to root user
sudo su 

## Create user with expiry date
useradd -e 2027-01-28 james

## Set password for the user
passwd james

# Verification

## Verify expiry date
chage -l james

# Output

## Account expires : Jan 28, 2027
