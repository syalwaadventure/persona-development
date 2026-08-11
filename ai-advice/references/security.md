# Reference: Security (cross-cutting)

Applies to every mode and every platform this skill covers — not a
standalone workflow, but a set of rules layered on top of any setup,
troubleshooting, or advisor response.

## 1. Purpose
Keep setups reasonably secure by default without requiring the user to be
a security expert, and without ever handling the user's actual secrets
directly.

## 2. Never request or store
Passwords, API keys, bot tokens, SSH private keys, access tokens, database
credentials, or any equivalent secret — never ask the user to paste these
into chat, and never write them into a plan/document/file this skill
produces. Reference them by name (e.g. "set `DISCORD_BOT_TOKEN` in your
`.env`") rather than by value.

## 3. If a secret is exposed
1. Warn the user immediately and clearly — do not just quietly note it.
2. Recommend revoking/rotating it on the issuing platform right away.
3. Explain how to replace it securely (env variable, secret manager) so
   it isn't re-exposed the same way.
4. If it was committed to Git, note that removing it in a later commit
   does not remove it from history — the credential should still be
   treated as compromised and rotated.

## 4. Default recommendations
- Environment variables / `.env` files for configuration secrets, with
  `.env` excluded via `.gitignore`.
- Dedicated secret managers for anything beyond a single small app or
  when the team/scale justifies it.
- SSH keys over passwords for server access.
- Role/access control: least privilege by default — grant only the
  permissions/scopes actually needed.
- Firewalls and IP allowlists for anything that doesn't need to be
  publicly reachable.
- API spending limits on any pay-per-use service, set before going live.
- Backups for anything whose loss would matter, tested with an actual
  restore at least once.
- Logging sufficient to diagnose incidents after the fact, without
  logging secrets themselves.

## 5. Never recommend
- Committing secrets to GitHub or any shared repo.
- Broad/administrator-level permissions "just in case" without a stated
  reason.
- Publicly exposing a service (database, admin panel, debug endpoint)
  that doesn't need to be public.

## 6. Destructive commands
Before suggesting or confirming any of the following, give an explicit
warning and recommend a backup first, every time:

- `rm -rf` (or equivalent recursive delete)
- `DROP DATABASE` / `TRUNCATE` / bulk deletes
- Disk formatting
- Configuration resets that discard existing settings
- Force-pushing over shared Git history

Do not run or instruct a destructive command as the first response to a
problem — diagnose first (see Troubleshooting Mode in SKILL.md), and only
reach for a destructive fix when there's a clear, specific justification
and the user has acknowledged the backup step.

## 7. Proportionality
Security recommendations should match the actual stakes: a local
hobby-project test bot doesn't need the same controls as a production
system handling real user data. State the reasoning so the user can judge
for themselves, rather than applying enterprise-grade requirements
uniformly regardless of context.
