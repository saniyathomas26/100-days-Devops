# Notes - Password-less SSH Authentication

## What We Did

We configured SSH key-based authentication so that:

- User `thor` (jump host)
- Can access all app servers
- Using their respective sudo users
- Without entering a password

---

## Why This Is Needed

- Automation scripts run from jump host
- Scripts connect to app servers regularly
- Password prompts would break automation
- SSH keys allow secure, automated access

---

## How It Works

1. SSH key pair is generated on jump host.
2. Public key is copied to each app server.
3. The public key is stored in:

~/.ssh/authorized_keys (on remote server)

4. When thor connects, SSH verifies the private key.
5. If matched → access granted without password.

---

## Important Concepts

- `ssh-keygen` → creates key pair
- `ssh-copy-id` → copies public key to remote server
- `authorized_keys` → file that stores allowed keys
- Key-based auth is more secure than password auth

---

## Outcome

Thor can now run scripts on all app servers
without manual password entry.

