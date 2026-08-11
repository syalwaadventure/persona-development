# Reference: Hostinger VPS

> Verify current specs, pricing, and panel UI against hostinger.com /
> Hostinger's official documentation — these change over time.

## 1. Purpose
Hostinger VPS provides a virtual private server with root access, sold in
tiers (KVM 1/2/4/8 etc.), suited for hosting websites, apps, bots, and small
services outside Hostinger's shared/managed hosting plans.

## 2. When to use it
- Need root/system-level access (shared hosting won't allow this).
- Running a Node/Python/Go app, a Discord bot, a database, or Docker
  containers that need to run continuously.
- Budget-conscious VPS with reasonable performance for small-to-medium
  workloads.

## 3. When NOT to use it
- A static site or simple WordPress site — shared or managed hosting is
  simpler and cheaper.
- Enterprise-scale workloads needing autoscaling, managed load balancers,
  multi-region redundancy — a cloud provider (AWS/GCP/Azure) fits better.
- Workloads requiring specific compliance certifications the provider
  doesn't offer — verify first.

## 4. Requirements
- Hostinger account and an active VPS plan.
- SSH client (Terminal on Mac/Linux, PuTTY or Windows Terminal on Windows).
- Basic familiarity with the Linux shell (or willingness to follow
  step-by-step, beginner mode).
- A domain name if the service needs to be publicly reachable by name.

## 5. Setup overview
1. Provision the VPS from hPanel — choose OS image (commonly Ubuntu LTS),
   region, and plan size based on expected workload.
2. Set the initial root password or SSH key during provisioning.
3. Connect via SSH (`ssh root@<vps-ip>`).
4. Update the system, create a non-root sudo user, harden SSH.
5. Install the required runtime/stack (see `deployment.md`,
   `linux-ubuntu.md`, `database.md` as relevant).
6. Configure firewall (Hostinger's panel firewall and/or `ufw`).
7. Point the domain's DNS A record to the VPS IP if public access is
   needed, then set up HTTPS (e.g. via Certbot/Let's Encrypt).

## 6. Key configuration concepts
- hPanel vs. shell: some settings (firewall rules, backups, snapshots, OS
  reinstall) are managed from hPanel; day-to-day app config is done over
  SSH.
- Resource tier selection should follow Section 10 decision logic in
  SKILL.md (workload → server size), not default to the biggest plan.
- Snapshots/backups in hPanel are separate from application-level backups
  (e.g. database dumps) — recommend both for anything important.

## 7. Validation
- `ssh` connects successfully with the intended user.
- `sudo -l` confirms the non-root user has appropriate privileges.
- Firewall (`ufw status` or hPanel firewall) shows only intended ports open.
- Application responds on its port locally (`curl localhost:<port>`) and,
  if public, from outside the network.
- If a domain is used, DNS resolves to the correct IP (`dig`/`nslookup`)
  and HTTPS certificate is valid.

## 8. Common errors
- `Permission denied (publickey)` on SSH: wrong key, key not added to
  `~/.ssh/authorized_keys`, or SSH password auth disabled without a key
  configured.
- Site unreachable after DNS change: DNS propagation delay (can take up to
  24-48h, usually faster) — check with `dig`.
- Out-of-memory kills on small plans: workload exceeds the VPS tier;
  consider upgrading or optimizing the app (see cost/resource logic in
  SKILL.md Section 8 before jumping to an upgrade).

## 9. Troubleshooting
- Diagnose before changing anything: check `htop`/`free -m` for
  resource pressure, `journalctl -u <service>` or app logs for crash
  reasons, `ufw status`/`netstat -tulpn` for connectivity issues.
- Isolate whether the problem is network (DNS/firewall/port), OS
  (service not running), or application (crash/misconfiguration) before
  proposing a fix.

## 10. Security considerations
- Disable root SSH login after creating a sudo user; prefer SSH keys over
  passwords.
- Keep `ufw` (or Hostinger's firewall) restricting inbound ports to only
  what's needed.
- Enable automatic security updates for the OS where reasonable.
- Never store credentials in plaintext scripts committed anywhere.

## 11. Cost considerations
- Plans are billed monthly/annually; longer terms are usually cheaper per
  month but less flexible.
- Factor in bandwidth limits and any add-ons (extra backups, dedicated IP)
  when estimating total cost — confirm current pricing on hostinger.com.

## 12. Maintenance
- Regular `apt update && apt upgrade` (or distro equivalent).
- Periodic review of running services and open ports.
- Scheduled backups/snapshots, tested by occasional restore drills.

## 13. Upgrade / scaling considerations
- Vertical scaling: upgrade to a larger VPS tier when CPU/RAM is
  consistently near capacity.
- Horizontal scaling / high availability generally exceeds what a single
  VPS offers — reconsider architecture (load balancer + multiple VPS, or
  a cloud provider) if that becomes a real requirement.
