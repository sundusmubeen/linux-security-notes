# Users and permissions

## Goals

- Create and manage least-privilege accounts
- Understand when to use `sudo`
- Read and set common file permissions

## Useful commands

```bash
# Who am I / groups
id
groups

# List users with login shells (high level check)
getent passwd

# Add a user (lab)
sudo adduser labuser

# Add to sudo group only if needed
sudo usermod -aG sudo labuser

# File permissions
ls -l file.txt
chmod 640 file.txt
chown user:group file.txt
```

## Permission reminder

| Mode | Meaning |
| --- | --- |
| `r` | read |
| `w` | write |
| `x` | execute / enter directory |
| `644` | owner rw, group/other r |
| `600` | owner only (good for private keys/config secrets) |
| `755` | common for directories and some binaries |

## Hardening habits

- Prefer named users over shared logins
- Give `sudo` only when required; remove when not needed
- Keep SSH keys at `600` and `~/.ssh` at `700`
- Do not leave world-writable scripts in shared folders

## What I practised

Explaining *why* a permission is wrong matters as much as running `chmod`. Interviewers often ask for that reasoning.
