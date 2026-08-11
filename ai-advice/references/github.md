# Reference: GitHub

> Confirm current UI/CLI flags against docs.github.com — settings pages
> and CLI syntax change periodically.

## 1. Purpose
GitHub hosts Git repositories and provides collaboration, CI/CD (Actions),
issue tracking, and deployment integration features.

## 2. When to use it
- Version control for any codebase, solo or team.
- Need CI/CD via GitHub Actions, or integration with deployment platforms
  that pull from GitHub.

## 3. When NOT to use it
- Purely local, throwaway scripts with no need for history/collaboration
  may not need a remote repo at all — though it's rarely harmful to use
  one anyway.
- Highly sensitive/regulated code may require a self-hosted or
  enterprise-controlled Git solution instead of public GitHub.

## 4. Requirements
- A GitHub account.
- Git installed locally (`git --version` to check).
- SSH key or HTTPS credential (personal access token) configured for
  authentication — GitHub no longer accepts plain passwords over HTTPS
  for git operations.

## 5. Setup overview
1. Install Git locally if not present.
2. Configure identity: `git config --global user.name "..."` and
   `git config --global user.email "..."`.
3. Set up authentication: SSH key (`ssh-keygen`, add public key to
   GitHub account) or a personal access token for HTTPS.
4. Create or clone a repository.
5. Add a `.gitignore` appropriate to the project's language/framework
   before the first commit, especially to exclude `.env`, credentials,
   and build artifacts.
6. Make an initial commit and push.
7. If CI/CD is needed, add a workflow under `.github/workflows/`.

## 6. Key configuration concepts
- SSH vs. HTTPS remotes: SSH avoids repeated token entry; HTTPS with a
  PAT is simpler to set up in constrained environments.
- Branch protection rules (in repo Settings) to require reviews/checks
  before merging to main, for team projects.
- Secrets for Actions are stored under repo/organization Settings →
  Secrets, never in the workflow file or committed code.

## 7. Validation
- `git remote -v` shows the correct remote URL.
- `git push` succeeds without authentication errors.
- If Actions is used, the workflow run shows green/passing status.
- `.gitignore` is actually excluding sensitive/generated files
  (`git status` shouldn't show them as trackable).

## 8. Common errors
- `Permission denied (publickey)`: SSH key not added to the GitHub
  account, or wrong key being used (`ssh -T git@github.com` to test).
- `remote: Support for password authentication was removed`: trying to
  use a password instead of a token/SSH key over HTTPS.
- Secret accidentally committed: treat as compromised — see Security
  section below and `references/security.md`.
- Merge conflicts: expected part of collaborative work — resolve by
  reviewing the conflicting sections, not by force-pushing over others'
  work without coordination.

## 9. Troubleshooting
- Confirm authentication works in isolation (`ssh -T git@github.com` or
  a simple `git ls-remote`) before debugging a specific push/pull
  failure.
- Check `git status` and `git log` to understand current repo state
  before making changes.

## 10. Security considerations
- If a secret is committed, rotate/revoke it immediately — removing it
  from a later commit does not remove it from history. Use tools like
  `git filter-repo` or GitHub's secret scanning remediation guidance, and
  still treat the original secret as compromised.
- Use branch protection and required reviews for anything beyond solo
  projects.
- Scope personal access tokens narrowly and set expirations.

## 11. Cost considerations
- Public repos and generous private repo usage are free on GitHub's
  standard plans; Actions minutes and storage have usage-based limits —
  confirm current limits for the account tier.

## 12. Maintenance
- Keep dependencies updated (Dependabot alerts if enabled).
- Periodically review and prune stale branches and unused Actions
  secrets.

## 13. Upgrade / scaling considerations
- For larger teams, consider CODEOWNERS, required status checks, and
  organization-level policies rather than ad hoc per-repo rules.
