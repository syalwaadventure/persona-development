# Reference: Application Deployment

> Deployment platforms and their UIs/CLIs change over time — confirm
> current specifics against the chosen platform's official docs.

## 1. Purpose
General guidance for taking an application from local development to a
running, reachable, persistent deployment — regardless of stack or target
platform (VPS, container platform, PaaS, serverless).

## 2. When to use it
- App works locally and needs to run somewhere else, reliably, possibly
  24/7 and/or publicly reachable.

## 3. When NOT to use it
- Purely local tools with no need for external access or persistence
  beyond the developer's own machine.

## 4. Requirements
- A working, tested local version of the app.
- Chosen target environment (VPS, container platform, PaaS) — see
  decision logic below.
- Environment variables/secrets separated from code, ready to be
  configured on the target platform.

## 5. Setup overview
1. Apply the decision logic (SKILL.md Section 10): 24/7 need, root access
   need, workload size, persistent storage need, public access need —
   this determines VPS vs. managed platform vs. serverless.
2. Prepare the app for deployment: externalize config via environment
   variables, add a process entry point appropriate to the platform
   (e.g. `Procfile`, `Dockerfile`, systemd unit).
3. Provision the target environment.
4. Deploy the app (push to platform, `docker run`/`docker compose up`,
   or copy + run via systemd on a VPS).
5. Configure a process manager or restart policy so the app survives
   crashes and reboots.
6. Set up domain + HTTPS if public access is needed (reverse proxy like
   Nginx/Caddy + Let's Encrypt is a common pattern on a VPS).
7. Set up basic logging/monitoring so failures are visible.

## 6. Key configuration concepts
- Process management: `systemd`, `pm2`, Docker restart policies, or the
  platform's built-in process supervision — pick one, don't leave the
  app running in a bare foreground terminal session for production.
- Reverse proxy (Nginx/Caddy) in front of the app for TLS termination and
  routing, rather than exposing the app's dev server directly to the
  internet.
- Zero-downtime vs. accept-brief-downtime deploys: only worry about
  zero-downtime tooling once the app has real users who'd notice a
  restart.

## 7. Validation
- App starts and responds to requests on the target environment.
- App survives a process crash (auto-restarts) and a full server reboot.
- If public: domain resolves, HTTPS certificate is valid, and the app is
  reachable from outside the host's own network.
- Logs are accessible for post-deploy debugging.
- Environment variables/secrets are present in the target environment
  correctly (without ever having the user paste actual secret values in
  chat).

## 8. Common errors
- App runs locally but not on the server: missing environment variables,
  different runtime version, or missing system dependency on the target
  host.
- Port already in use: another process bound to the same port — check
  with `lsof -i :<port>` or platform equivalent.
- 502/504 from reverse proxy: app isn't actually running or is listening
  on the wrong port/interface (e.g. bound to `127.0.0.1` when the proxy
  expects a different bind).
- App dies silently after SSH session closes: was run in the foreground
  of an interactive shell without a process manager — needs `systemd`/
  `pm2`/`nohup`+ proper supervision, not just backgrounding with `&`.

## 9. Troubleshooting
- Confirm the process is actually running on the target host before
  debugging networking (`ps aux`, `systemctl status`).
- Check application logs for the actual startup error before assuming
  it's an infrastructure issue.
- Isolate layer by layer: process running? → listening on expected
  port/interface? → reverse proxy routing correctly? → DNS/HTTPS correct?

## 10. Security considerations
- Never expose a dev/debug server directly to the public internet in
  production — use a proper WSGI/ASGI server, process manager, and
  reverse proxy as appropriate to the stack.
- Secrets via environment variables/secret manager, not committed config
  files.
- Firewall restricts inbound ports to what's actually needed (80/443 for
  a web app, plus SSH).

## 11. Cost considerations
- Start with the smallest instance/tier that plausibly fits the expected
  workload; monitor actual usage before upgrading.
- Factor in bandwidth and storage costs, not just compute, for the
  chosen platform.

## 12. Maintenance
- Keep runtime and dependencies updated.
- Monitor logs/uptime; set up basic alerting if the app is
  business-critical.

## 13. Upgrade / scaling considerations
- Containerizing the app (Docker) early makes later horizontal scaling
  or platform migration significantly easier, even for a single-instance
  deployment today.
