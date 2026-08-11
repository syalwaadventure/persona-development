# Reference: OpenRouter

> Confirm current model list, pricing, and endpoint details at
> openrouter.ai/docs — these change frequently.

## 1. Purpose
OpenRouter provides a unified API to access many different LLMs from
multiple providers through one API key and OpenAI-compatible interface.

## 2. When to use it
- Want to try/compare multiple LLM providers without separate accounts
  and integrations for each.
- Want fallback routing across providers/models for reliability.
- Building an app that should be model-agnostic or easily swappable.

## 3. When NOT to use it
- Need a provider-specific feature not exposed through OpenRouter (check
  current docs for feature parity).
- Strict data-residency/compliance requirements that require a direct
  enterprise agreement with a specific model provider.

## 4. Requirements
- OpenRouter account and an API key.
- HTTPS client capability in the app (most languages/frameworks have one).
- A way to store the API key securely (env variable / secret manager) —
  never hardcoded or committed to source control.

## 5. Setup overview
1. Create an OpenRouter account and generate an API key from the
   dashboard.
2. Store the key as an environment variable (e.g. `OPENROUTER_API_KEY`),
   not in code.
3. Point the app's HTTP client at OpenRouter's API base URL (per current
   docs) using the OpenAI-compatible chat completions format.
4. Select a model identifier from OpenRouter's current model list.
5. Set a spending limit/budget alert in the dashboard before going to
   production.
6. Test with a minimal request before wiring it into the full app.

## 6. Key configuration concepts
- Model routing: OpenRouter lets you specify fallback models; useful for
  resilience but confirm cost implications per model.
- Headers: some integrations require optional attribution headers
  (referrer/app name) — check current docs.
- Rate limits and per-model pricing vary — do not assume uniform cost
  across models.

## 7. Validation
- A minimal test request returns a successful completion (HTTP 200) with
  expected response shape.
- Error responses (401, 402, 429) are handled gracefully in the app, not
  just on the happy path.
- Spending/usage shown in the OpenRouter dashboard matches expected test
  volume.

## 8. Common errors
- `401 Unauthorized`: invalid/missing API key, or key not passed in the
  correct header format.
- `402`/insufficient credit: account balance or spend limit reached.
- `429 Too Many Requests`: rate limit hit — check current rate limits for
  the account tier and add backoff/retry logic.
- Unexpected model behavior: confirm the exact model identifier string is
  correct and current (these are sometimes renamed/deprecated).

## 9. Troubleshooting
- Reproduce the failing request with a minimal `curl` call to isolate
  whether the issue is in the app code or the API call itself.
- Check the response body's error message before assuming the cause.
- Confirm the API key hasn't been rotated/revoked and that billing is
  active.

## 10. Security considerations
- Never expose the API key in client-side/frontend code — route calls
  through a backend.
- Set spending limits to cap exposure if the key is ever leaked.
- Rotate the key immediately if it's ever pasted into a public place
  (chat, repo, log).

## 11. Cost considerations
- Cost is usage-based (per token, varies by model) — estimate based on
  expected request volume and typical prompt/response length, and label
  the estimate as approximate.
- Cheaper models may be sufficient for non-critical tasks; reserve
  premium models for cases that need them.

## 12. Maintenance
- Periodically review which models are in use vs. deprecated/renamed.
- Monitor usage/cost dashboards, especially after any app changes that
  increase call volume.

## 13. Upgrade / scaling considerations
- For higher volume, plan for retry/backoff, caching repeated requests
  where sensible, and monitoring cost per feature as usage grows.
