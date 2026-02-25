
# Command Executed
## Connect to App Server 1, 2& 3
ssh tony@stapp01
sudo su

## Install and Enable iptables
yum install -y iptables-services
systemctl enable iptables
systemctl start iptables
## Firewall Configuration
Allow access to port 5002 from Load Balancer (stlb01)

iptables -A INPUT -p tcp -s stlb01 --dport 5002 -j ACCEPT

Block access to port 5002 from all other sources

iptables -A INPUT -p tcp  --dport 5002 -j DROP
## Verify Rules
iptables -L INPUT --line-numbers -n -v
## Cleanup Default Reject Rule

Line number 5 says REJECT ALL

iptables -D INPUT 5
## Apply Rules
service iptables save
systemctl restart iptables
