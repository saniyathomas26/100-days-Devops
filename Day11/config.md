# Day 11 – Tomcat Configuration (Port 6300)

## Overview

This document describes the configuration changes performed on **App Server 3 (stapp03)** for deploying the application using Apache Tomcat.

---

## 1️⃣ Tomcat Installation

Tomcat was installed using:

sudo yum install -y tomcat

---

## 2️⃣ Tomcat Port Configuration

By default, Tomcat runs on port **8080**.
The requirement was to configure it to run on **port 6300**.

### Configuration File Location

/etc/tomcat/server.xml

### Edit Command

sudo vi /etc/tomcat/server.xml

---

### Default Connector Configuration

<Connector port="8080" protocol="HTTP/1.1"
        connectionTimeout="20000"
        redirectPort="8443" />

---

### Updated Connector Configuration

<Connector port="6300" protocol="HTTP/1.1"
        connectionTimeout="20000"
        redirectPort="8443" />

---

## 3️⃣ Service Management

After modifying the configuration, Tomcat service was restarted:

sudo systemctl restart tomcat

To verify the service status:

sudo systemctl status tomcat

---

## 4️⃣ Application Deployment Configuration

The application was deployed by placing the WAR file inside:

/usr/share/tomcat/webapps/

Deployment command used:

sudo mv /home/banner/ROOT.war /usr/share/tomcat/webapps/

Tomcat automatically extracts and deploys the WAR file when placed inside the `webapps` directory.

Since the file was named `ROOT.war`, the application becomes accessible directly at:

[http://stapp03:6300](http://stapp03:6300)

---

## Final Result

Tomcat successfully runs on port **6300**, and the deployed application is accessible using:

curl [http://stapp03:6300](http://stapp03:6300)

---

✅ Port reconfigured (8080 → 6300)
✅ Service restarted
✅ Application deployed via ROOT.war
✅ Base URL access verified
