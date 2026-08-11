# AI Advice — Skill README

AI Advice is a general technical setup advisor skill. It helps with
installation, configuration, deployment, troubleshooting, validation, and
technical recommendations for software, platforms, servers, tools, and
applications — not limited to AI-related tools.

## How it works

`SKILL.md` is the core behavior file: intake questions, the four working
modes (Advisor / Setup / Troubleshooting / Validation), user-level
adaptation, language behavior, security rules, cost-awareness, decision
logic, routing, output formats, and session memory rules. It's the only
file read on every invocation.

`references/` holds platform-specific knowledge (Hostinger, Linux/Ubuntu,
OpenRouter, Discord, GitHub, ETAP, database, deployment, API integration,
security). These are loaded on demand — only the reference matching the
platform in the user's request gets read, keeping the skill lightweight
and easy to extend. Adding a new platform means adding a new file here;
`SKILL.md` never needs to change for that.

`templates/` holds reusable output skeletons (setup checklist,
troubleshooting template, validation checklist, comparison template) that
keep responses consistent across sessions and modes.

## Adding a new platform

1. Create `references/<platform>.md` following the same 13-section shape
   used in the existing files (purpose, when to use, when not to use,
   requirements, setup overview, key configuration concepts, validation,
   common errors, troubleshooting, security, cost, maintenance, upgrade/
   scaling).
2. Mark anything that could go stale (pricing, exact UI steps, version
   numbers) as "verify against official docs."
3. No changes to `SKILL.md` are needed — routing is intent-based, not a
   hardcoded platform list.

## Example user prompts

- "cara setup VPS Hostinger buat bot Discord" (Setup Mode, Hostinger +
  Discord + Linux references, Indonesian)
- "should I use a VPS or a managed platform for a Node app with ~50 users?"
  (Advisor Mode, deployment reference)
- "my Discord bot is online but doesn't respond to messages" (Troubleshooting
  Mode, discord.md)
- "is my Ubuntu server setup actually secure?" (Validation Mode, security.md
  + linux-ubuntu.md)
- "gagal connect ke license server ETAP" (Troubleshooting Mode, etap.md,
  Indonesian)
- "help me connect my GitHub repo to auto-deploy on my VPS" (Setup Mode,
  github.md + deployment.md + hostinger.md)

## Example routing behavior

User message mentions "VPS" + "Discord bot" + "cara setup" → Setup Mode,
Indonesian response, reads `hostinger.md` (or general VPS guidance if a
different provider is named) and `discord.md`, uses
`templates/setup-checklist.md` as the running structure.

## Example setup workflow

1. Intake: confirm OS/environment already chosen, ask only what's
   materially missing (e.g. "is this for testing or does it need to run
   24/7?").
2. State assumptions if proceeding without asking further.
3. Walk one phase at a time using the STEP format from `SKILL.md` Section
   4B.
4. After each phase, validate before moving to the next.
5. End with a Validation Mode pass and a security check before calling it
   done.

## Example troubleshooting workflow

1. Take the error/symptom as given — don't ask for information already
   provided.
2. List 1–3 likely causes, ranked.
3. Run the safest diagnostic first; ask the user to run it if Claude
   can't directly.
4. Apply the narrowest fix for the confirmed cause.
5. Validate the fix actually resolved it (not just "no error now").
6. Only escalate to a bigger/more destructive fix if the narrow fix
   didn't work and there's a backup in place.

## Validation checklist

See `templates/validation-checklist.md` for the standard component/status/
evidence/issue/action table used to confirm a setup is genuinely working
before it's declared complete.

## Notes for future migration (e.g. into Hermes Agent)

- The skill is self-contained: `SKILL.md` + `references/` + `templates/`
  with no external dependencies beyond the assistant's own web-search/doc
  lookup capability for verifying current platform details.
- Reference files are additive — new platforms can be dropped in without
  touching core behavior.
- All security rules (no secret handling, destructive-command warnings)
  are centralized in `references/security.md` and referenced from
  `SKILL.md`, so they apply uniformly regardless of platform.
