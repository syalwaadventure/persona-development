# Reference: Platform / API Integration

> Confirm current auth flows, scopes, and endpoints against each
> platform's own official docs — integration details change often.

## 1. Purpose
General guidance for connecting two systems/platforms together via APIs,
webhooks, or a middleware/automation layer (e.g. connecting a CRM to a
chat app, syncing data between two SaaS tools, wiring a bot to a backend).

## 2. When to use it
- User wants two systems to talk to each other (e.g. Discord ↔ database,
  GitHub ↔ Slack, app ↔ third-party API).

## 3. When NOT to use it
- If a no-integration solution (manual process, single-platform native
  feature) fully satisfies the need with far less complexity, mention
  that as an option before building a custom integration.

## 4. Requirements
- API access/credentials for both systems (API key, OAuth app, or
  webhook URL) — obtained by the user directly from each platform, never
  pasted into chat as raw secret values.
- Understanding of each platform's rate limits and auth model
  (API key, OAuth2, HMAC-signed webhooks, etc.).
- A place to run the integration logic if it's not a no-code platform
  (see `deployment.md`).

## 5. Setup overview
1. Clarify the direction and trigger of the integration: which system
   initiates, what event triggers a sync, and what data actually needs
   to flow (avoid syncing more than necessary).
2. Confirm the auth model each platform requires (API key, OAuth2 with
   specific scopes, signed webhooks) and set up credentials on each side.
3. Decide sync approach: polling (the integration checks periodically) vs.
   webhook/event-driven (the platform notifies on change) — event-driven
   is usually more efficient and timely when supported.
4. Build/configure the integration logic (custom code, or a no-code tool
   like Zapier/Make/n8n if that fits the user's technical level and
   needs).
5. Handle failures: retries with backoff, idempotency (avoid duplicate
   actions on retry), and logging of failed syncs.
6. Test end-to-end with a real but low-stakes event before relying on it
   for anything critical.

## 6. Key configuration concepts
- Webhook signature verification: verify the payload signature/secret
  where the platform supports it, to avoid accepting spoofed webhook
  calls.
- Idempotency: design the integration so re-processing the same event
  twice (which happens with retries) doesn't cause duplicate side
  effects.
- Least-privilege scopes: request only the OAuth scopes/API permissions
  actually needed for the integration.

## 7. Validation
- A real trigger event on Platform A produces the expected result on
  Platform B within an acceptable time window.
- Duplicate/retry events don't cause duplicate actions.
- Auth tokens are being refreshed correctly if using OAuth with expiring
  tokens.
- Failures are logged somewhere the user can actually see them.

## 8. Common errors
- `401`/`403` from one side: expired/invalid token, or insufficient
  scope — check which specific scope the failing call requires.
- Webhook never received: URL not publicly reachable, signature
  verification misconfigured causing silent rejection, or the webhook
  wasn't actually registered/subscribed on the source platform.
- Rate limiting (`429`): too frequent polling or bursty calls — add
  backoff and, where possible, switch from polling to webhooks.
- Data mismatch/duplication: missing idempotency handling on retries.

## 9. Troubleshooting
- Test each side of the integration independently first (does Platform A
  actually fire the event? does Platform B accept a manually-crafted
  test call?) before debugging the integration as a whole.
- Check both platforms' delivery/webhook logs (many provide a log of
  recent webhook attempts and response codes) before assuming the
  problem is in your code.

## 10. Security considerations
- Store all credentials/tokens for both platforms in environment
  variables or a secret manager.
- Verify webhook signatures where supported, rather than trusting any
  request to the webhook URL.
- Use HTTPS endpoints for anything receiving webhooks or handling
  credentials.

## 11. Cost considerations
- No-code automation platforms often have run/task-based pricing tiers —
  estimate expected event volume against the platform's free/paid tier
  limits before committing.
- Custom code avoids per-task platform fees but adds hosting/maintenance
  cost — weigh against the team's technical capacity.

## 12. Maintenance
- Monitor for API deprecations/breaking changes on either platform.
- Periodically review granted scopes/permissions and revoke anything no
  longer needed.

## 13. Upgrade / scaling considerations
- Move from polling to webhooks as volume grows, if not already
  event-driven, to reduce load and latency.
