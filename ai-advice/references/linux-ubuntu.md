# Reference: Linux / Ubuntu

> Verify exact package names/versions against `man` pages or
> ubuntu.com/server/docs — package availability differs across Ubuntu
> releases (LTS vs. non-LTS).

## 1. Purpose
Ubuntu is a Debian-based Linux distribution commonly used as a server OS
for VPS, cloud instances, and self-hosted services.

## 2. When to use it
- Any server workload needing a stable, widely-supported Linux base with
  long-term support (LTS releases).
- When the user's app/tooling documents Ubuntu/Debian as the primary
  supported OS.

## 3. When NOT to use it
- If the target software only documents/supports another distro (e.g.
  specific RHEL/CentOS-only enterprise tooling) — check compatibility
  first.
- Extremely resource-constrained embedded devices may prefer a lighter
  distro.

## 4. Requirements
- SSH or console access to the machine.
- A user with `sudo` privileges for administrative tasks.

## 5. Setup overview (baseline hardening + readiness)
1. `sudo apt update && sudo apt upgrade -y` — bring packages current.
2. Create a non-root user: `sudo adduser <username>` then
   `sudo usermod -aG sudo <username>`.
3. Configure SSH: prefer key-based auth, disable root login and password
   auth once a key-based non-root user works (edit
   `/etc/ssh/sshd_config`, then `sudo systemctl restart ssh`).
4. Set up a firewall: `sudo ufw allow OpenSSH`, `sudo ufw enable`, then
   allow only the ports the app actually needs (e.g. `sudo ufw allow 80,443/tcp`).
5. Set timezone and hostname if relevant (`timedatectl`, `hostnamectl`).
6. Install the runtime/stack needed for the specific application.

## 6. Key configuration concepts
- Package management: `apt` for most software; some tools ship via
  official third-party repos, snaps, or manual binaries — prefer the
  vendor's official install method.
- Services are typically managed via `systemd`
  (`systemctl start/stop/enable/status <service>`).
- Logs: `journalctl -u <service>` for systemd-managed services;
  `/var/log/` for many others.

## 7. Validation
- `whoami` / `id` confirm the correct user and group membership.
- `sudo ufw status verbose` shows only intended ports open.
- `systemctl status <service>` shows `active (running)` for required
  services.
- `df -h`, `free -m`, `uptime` for a basic resource/health snapshot.

## 8. Common errors
- `Permission denied` on file operations: ownership/permission mismatch —
  check with `ls -l`, fix with `chown`/`chmod` deliberately (avoid
  blanket `chmod -R 777`, which is a security risk).
- Service fails to start: check `journalctl -xeu <service>` for the
  actual error before assuming a fix.
- `apt` lock errors (`Could not get lock`): another package process is
  running; wait or check `ps aux | grep apt` rather than force-killing
  blindly.

## 9. Troubleshooting
- Reproduce the failure, check the specific service's logs, isolate
  whether it's a config, permissions, dependency, or resource issue, then
  apply the narrowest fix.
- Avoid `sudo reboot` or reinstalling packages as a first response —
  diagnose first.

## 10. Security considerations
- Key-based SSH auth, root login disabled, `ufw` enabled with minimal
  open ports.
- Enable unattended security upgrades where appropriate
  (`unattended-upgrades` package).
- Keep sensitive config out of world-readable files; use proper file
  permissions for credentials (`chmod 600`).

## 11. Cost considerations
- Ubuntu itself is free; cost is driven by the hosting/VPS/cloud
  instance running it. Right-size the instance to the workload.

## 12. Maintenance
- Regular updates, periodic audit of installed packages and open ports,
  log rotation (`logrotate`, usually preconfigured).

## 13. Upgrade / scaling considerations
- LTS-to-LTS upgrades (`do-release-upgrade`) should be planned and
  backed up first — not run casually on a production box.
- For scaling beyond one box, consider containerization (Docker) or
  orchestration rather than manually replicating server config.
