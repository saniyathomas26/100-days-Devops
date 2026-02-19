# Day 09 - Fixing MariaDB Service Issue

## Issue

The Nautilus application was not able to connect to the database.

After checking, we found that the MariaDB service was not running on the database server.

---

## Step 1: Check MariaDB Service Status

Command:
systemctl status mariadb

Purpose:
To check whether the MariaDB service is running or not.

Result:
Service was not running.

---

## Step 2: Try Restarting MariaDB

Command:
systemctl restart mariadb

Purpose:
To restart the MariaDB service and bring it back online.

But the service failed again.

---

## Step 3: Check Detailed Logs

Command:
journalctl -xeu mariadb.service

Purpose:
To check detailed error logs related to the MariaDB service.

From logs, it was identified that the MySQL data directory was missing.

---

## Step 4: Create MySQL Data Directory

Command:
cd /var/lib
mkdir /var/lib/mysql

Purpose:
MariaDB stores database files inside /var/lib/mysql.
Since the folder was missing, we created it manually.

---

## Step 5: Set Correct Ownership

Command:
chown -R mysql:mysql mysql

Purpose:
MariaDB runs with the mysql user.
So we gave ownership of the folder to mysql user and group.

---

## Step 6: Restart MariaDB Again

Command:
systemctl restart mariadb

Now the service started successfully.

---

## Step 7: Verify Service Status

Command:
systemctl status mariadb

Result:
Service is active and running.

---

## Final Result

- MariaDB service is running.
- Application can now connect to the database.
- Issue resolved.
