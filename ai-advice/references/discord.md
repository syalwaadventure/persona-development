# Reference: Discord Bot Setup

> Confirm current Developer Portal UI, intents, and API version against
> discord.com/developers/docs — these change periodically.

## 1. Purpose
Guidance for creating, configuring, hosting, and troubleshooting a Discord
bot (application) that connects to a server (guild) via the Discord API.

## 2. When to use it
- Building automation, moderation, or interactive features for a Discord
  community.
- Integrating Discord notifications/commands with another system.

## 3. When NOT to use it
- If the need is a one-off manual action, a bot may be overkill vs. using
  existing Discord features (webhooks, built-in automod) directly.

## 4. Requirements
- A Discord account and a server (guild) where the bot can be added, with
  "Manage Server" permission.
- A hosting environment for the bot process that can run continuously if
  it needs to be online 24/7 (see SKILL.md Section 10 decision logic —
  local machine is fine for testing, a VPS/cloud service for production).
- A programming environment with a Discord library (e.g. discord.js,
  discord.py) matching the bot's language.

## 5. Setup overview
1. Create an application in the Discord Developer Portal, then add a Bot
   user to it.
2. Copy the bot token immediately into a secure location (env variable /
   secret manager) — treat it like a password; do not paste it into chat
   or commit it to source control.
3. Enable only the intents the bot actually needs (e.g. Message Content
   Intent) under the Bot settings.
4. Generate an OAuth2 invite URL with the minimum required scopes/
   permissions, and use it to add the bot to the target server.
5. Write the bot logic using the chosen library, reading the token from
   an environment variable.
6. Run the bot locally first to confirm it comes online and responds.
7. Deploy to a persistent host (VPS, container, or managed process
   runner) if it needs to run 24/7, with a process manager
   (e.g. `pm2`, `systemd`, or Docker restart policies) to auto-restart on
   crash.

## 6. Key configuration concepts
- Intents: Discord requires explicitly enabling privileged intents
  (message content, presence, members) both in code and in the Developer
  Portal — mismatches are a very common cause of bots "not seeing"
  messages.
- Permissions: grant the bot only the permissions it needs in the invite
  URL and per-channel overrides — avoid blanket Administrator unless
  genuinely required.
- Slash commands vs. message-based commands: slash commands are the
  current recommended interaction model; registration can be
  guild-scoped (instant, good for testing) or global (slower to
  propagate, for production).

## 7. Validation
- Bot shows as online in the server member list.
- A basic command/interaction gets a response.
- Bot survives a process restart and reconnects automatically.
- Logs show no repeated reconnect/auth errors.

## 8. Common errors
- Bot online but not responding to messages: Message Content Intent not
  enabled (in portal and/or code).
- `401 Unauthorized` / login failure: invalid or revoked token, or token
  pasted with extra whitespace/quotes.
- Missing permissions error on an action: bot's role lacks the specific
  permission, or role hierarchy places the bot below the target role.
- Slash commands not appearing: registration not yet propagated (global
  commands can take up to ~1 hour) or registered against the wrong
  application/guild ID.

## 9. Troubleshooting
- Confirm the process is actually running and connected (check logs for
  a successful "ready"/"logged in" event) before debugging command logic.
- Isolate whether the issue is connection (token/intents), permissions
  (role/scope), or command logic (code bug) before changing config.

## 10. Security considerations
- Treat the bot token as a secret equivalent to a password; rotate it
  immediately in the Developer Portal if ever exposed.
- Store the token via environment variable / `.env` (excluded via
  `.gitignore`), never hardcoded.
- Grant least-privilege permissions on the invite URL.

## 11. Cost considerations
- Discord bot usage itself is free; cost comes from the hosting
  environment if it needs to run 24/7 — a small VPS or free-tier host is
  usually sufficient for light bots.

## 12. Maintenance
- Keep the bot library updated (breaking API changes happen periodically).
- Monitor for deprecation notices from Discord (e.g. intent or API
  version changes).

## 13. Upgrade / scaling considerations
- For bots in many servers, consider sharding per the library's guidance
  once Discord requires it (based on guild count thresholds — check
  current docs).
