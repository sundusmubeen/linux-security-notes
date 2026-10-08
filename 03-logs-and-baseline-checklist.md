# Logs and baseline checklist

## Useful log locations (Ubuntu-style)

| Path / source | Why it matters |
| --- | --- |
| `/var/log/auth.log` | Logins, sudo, SSH auth events |
| `/var/log/syslog` | General system messages |
| `journalctl -u ssh` | SSH service-focused view |
| `last` / `lastb` | Recent logins / failed attempts |

```bash
sudo tail -n 50 /var/log/auth.log
sudo journalctl -u ssh -n 50 --no-pager
last -a | head
```

## Baseline hardening checklist (lab VM)

- [ ] Unique user accounts; no shared admin login
- [ ] SSH key auth preferred; password auth limited if possible
- [ ] Unused packages/services removed or disabled
- [ ] Host firewall on; only required ports open
- [ ] Automatic security updates enabled where appropriate
- [ ] Critical files not world-writable
- [ ] Know where auth logs live before an incident happens

## Tie-in to IR

Knowing log paths before an alert saves time during containment and analysis. This checklist is meant to sit beside the incident-response lab notes.
