# Day 02 – SSH Security Hardening

## Task
Disable direct SSH login for the root user.

## Server
All App Servers (Stratos Datacenter)

## Purpose
Disabling direct root SSH login is a security best practice. It reduces the risk of attacks and unauthorized access. Administrators should log in using a normal user account and escalate privileges using sudo, ensuring better auditability and access control.

## Verification
After updating the configuration:
Restart the SSH service.
Attempting to log in directly as root via SSH should be denied.
Non-root users with proper permissions should still be able to access the server.
