
# Day06
## Task:
Install cronie on all app servers, start the crond service, and configure a cron job for the root user to run every 5 minutes.

## Purpose:
To validate that the cron daemon is correctly installed, enabled, and capable of executing scheduled jobs with root privileges, ensuring the environment is ready for deploying automated maintenance and operational scripts.

## Cron Job Explanation:
*/5 * * * * echo hello > /tmp/cron_text
- */5 → Runs every 5 minutes
