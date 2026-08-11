# Setup Checklist Template

Use this to track a multi-step Setup Mode session. Fill in as steps are
completed; keep it updated across the conversation so nothing is re-asked
or re-done unnecessarily.

## Current Condition
- Device / OS:
- Environment (local / VPS / cloud):
- Already completed:
- User technical level:

## Goal
-

## Requirements
-

## Architecture / Setup Overview
Brief description of the target end state (what will be running, where,
how it's reached).

## Step-by-Step Setup

| # | Step | Status | Notes |
|---|------|--------|-------|
| 1 |      | [ ] pending / [~] in progress / [x] done | |
| 2 |      | | |
| 3 |      | | |

For the step currently in progress, expand using:

```
STEP X — Step Name
Goal:
Action:
Expected Result:
Validation:
If It Fails:
```

## Validation
See `validation-checklist.md` once all steps are done.

## Security Check
- [ ] No secrets requested/pasted in chat
- [ ] Credentials stored via env var / secret manager
- [ ] Firewall/ports restricted to what's needed
- [ ] Backup exists before any destructive step

## Final Status
[✓ / ⚠ / ✗ / ?] — overall

## Next Step
-
