
# Commands Executed
## Connect to DB server
ssh peter@stlb01

## Taking sudo permission for creating DB user and password
sudo -u postgres sql

CREATE USER kodekloud_rin WITH PASSWORD 'GYkqjdhdc';

CREATE DATABASE kodekloud_db10;

GRANT ALL PRIVILEGES ON DATABASE kodekloud_10 TO kodekloud_rin;
