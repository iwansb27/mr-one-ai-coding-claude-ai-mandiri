# Cost and Free-Tier Gate

**Policy:** Free-first, not free-at-any-cost. No paid subscription, billing activation, or paid API use without Iwan's explicit approval.

## Required checks before selecting a provider

| Check | Current status | Evidence to record |
|---|---|---|
| Account eligibility / region | UNTESTED | Current provider documentation |
| Email, phone, or identity verification | UNTESTED | Official signup requirements |
| Payment card required | UNTESTED | Official billing/FAQ page |
| Free quota and rate limits | UNTESTED | Dated quota details and reset period |
| Model availability | UNTESTED | Exact model IDs and availability |
| Endpoint/API compatibility with FCC | UNTESTED | Official API docs plus harmless test |
| Quota exhaustion behavior | UNTESTED | Whether requests stop, throttle, or require billing |
| Automatic charges possible | UNTESTED | Billing configuration and safeguards |
| Expiration or policy changes | UNTESTED | Review date and source link |
| Prompt/code retention and training terms | UNTESTED | Current provider data terms |

## Guardrails
- A free API key does not imply unlimited or permanent free use.
- Do not add a payment method just to continue unless Iwan explicitly approves.
- If pricing, quota, or billing behavior is unclear, stop and mark BLOCKED.
- Set usage alerts/limits if the provider supports them, but do not assume an alert prevents charges.
- Never publish API keys in this public repository.

## Candidate research links
- NVIDIA API keys: https://build.nvidia.com/settings/api-keys
- NVIDIA model catalog: https://build.nvidia.com/

These are research starting points, not confirmation of current free access.
