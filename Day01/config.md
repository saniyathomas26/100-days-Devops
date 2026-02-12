Command Executed

Connect to App Server 3 -
ssh banner@stapp03

Switch to root user -
sudo su

Adding user Jim with a non-interactive shell -
useradd -s /sbin/nologin jim passwd

Verification of user entry -
grep jim /etc/passwd

Output -
jim:x:1003:1003::/home/jim:/sbin/nologin
