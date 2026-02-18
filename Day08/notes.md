# Day 08 - Ansible Installation on Jump Host

## Objective
Install Ansible version 4.8.0 on the Jump Host using pip3 and make it available globally for all users.

---

## Why Ansible?
- Agentless (No need to install on client machines)
- Uses SSH
- Simple configuration
- Written in Python

---

## Steps Performed

### 1. Switched to root user
sudo su

### 2. Installed Ansible using pip3
pip3 install ansible==4.8.0

### 3. Verified Ansible Installation
ansible --version

Output confirmed:
- ansible-core 2.11.12
- ansible 4.8.0
- Installed in /usr/local/bin/ansible

---

## Important Note

Ansible was installed using pip3 as root user, which installs it globally under:

/usr/local/bin/

Because of this:
- All system users can run `ansible` command.
- No virtual environment was used.
