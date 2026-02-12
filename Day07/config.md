# Day 07 - Password-less SSH Setup

## Objective
Enable password-less SSH access from user `thor` (jump host)
to all app servers using their respective sudo users.

---

## Step 1: Switch to thor user (on jump host)

whoami
# Make sure you are thor

---

## Step 2: Generate SSH Key (if not already created)

ssh-keygen -t rsa

# Press Enter for default location
# Press Enter for no passphrase

This creates:
~/.ssh/id_rsa
~/.ssh/id_rsa.pub

---

## Step 3: Copy Public Key to App Servers

### App Server 1 (sudo user: tony)

ssh-copy-id tony@app-server1

### App Server 2 (example)

ssh-copy-id steve@app-server2

### App Server 3 (example)

ssh-copy-id banner@app-server3

---

## Step 4: Test Password-less Login

ssh tony@app-server1
ssh steve@app-server2
ssh banner@app-server3

If login works without password → setup successful ✅

