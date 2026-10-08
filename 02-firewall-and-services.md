# Firewall and services

## Goals

- See what is listening on a host
- Reduce unnecessary exposure
- Apply simple host firewall rules in a lab

## See what is open

```bash
# Listening ports (modern)
ss -tulpn

# Or
sudo netstat -tulpn

# Running services (systemd)
systemctl list-units --type=service --state=running
```

## UFW examples (Ubuntu lab)

```bash
sudo ufw status verbose
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow OpenSSH
sudo ufw enable
```

Only open what the lab role needs (for example SSH, or a specific app port).

## Service hygiene

1. Identify each listening service and its purpose.
2. Disable unused services.
3. Bind services to localhost when remote access is not required.
4. Re-check with `ss -tulpn` after changes.

## What I practised

Linking open ports back to real services — and deciding whether each one should stay exposed.
