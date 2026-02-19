# Day 09 - Configuration Details

## Service Name
mariadb

## Service Management Tool
systemctl (Systemd)

## Log Checking Command
journalctl -xeu mariadb.service

## Database Data Directory
/var/lib/mysql

## Required Ownership
User: mysql
Group: mysql

Command Used:
chown -R mysql:mysql /var/lib/mysql

## Root Cause
The MySQL data directory (/var/lib/mysql) was missing.

## Resolution
- Created missing directory
- Assigned correct ownership
- Restarted MariaDB service

## Final Status
MariaDB service is active and running.
