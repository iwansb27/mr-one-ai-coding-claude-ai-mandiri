# MR.ONE Claude AI Coding Mandiri — Checkpoint

**Checkpoint ID:** FCC-PLAN-002  
**Status:** UNTESTED / PLANNING  
**Owner:** Iwan  
**Repository:** https://github.com/iwansb27/mr-one-ai-coding-claude-ai-mandiri  
**Visibility:** Public  
**Review date:** 2026-10-16

## Completed
- Existing master blueprint prepared and stored in ChatGPT Library.
- Repository created and core planning files committed and read back.
- FCC upstream README, LICENSE, installer scripts, pyproject.toml, and uv.lock were fetched through GitHub and reviewed at a preliminary level.
- FCC current license is **AGPL-3.0-only** (not MIT); README requires **Python 3.14.7** and uses uv.
- Installer scripts set up FCC plus selected coding agents and fetch external installers/packages; therefore the one-line remote installer must not be run without further review.
- NVIDIA model catalog currently distinguishes “Free Endpoint” from “Download Available”; free hosted endpoints are limited and model/account-specific.
- Plan keeps FCC separate from the MR.ONE Autonomous Cloud Agent blueprint.

## Preliminary upstream findings — not a full security audit
- Upstream: https://github.com/Alishahryar1/free-claude-code
- The README describes FCC as an independent project, not affiliated with or endorsed by Anthropic.
- LICENSE states AGPL-3.0-only; review obligations before redistributing modified versions or offering a modified network service.
- pyproject.toml pins the Python requirement to exactly 3.14.7; laptop OS and compatibility remain unverified.
- scripts/install.sh and scripts/install.ps1 download/run additional software installers and packages. Reading their first sections is not equivalent to a complete line-by-line installer/security audit.
- NVIDIA hosted free endpoints are trial/prototyping access; current quotas/rate limits vary by model/account and can change. Do not assume unlimited or permanent free access.
- No code has been installed or executed as part of this review.

## Not completed
- Full line-by-line installer and updater review, including download verification, persistence, shell/profile changes, privilege behavior, and remote update chain.
- Dependency/supply-chain review and confirmation of pinned release/version integrity.
- Confirmation of supported laptop OS and hardware.
- Provider account eligibility, exact model endpoint, quota, rate limits, billing safeguards, and data-retention terms for Iwan's account.
- Installation or runtime testing.
- Sandbox acceptance tests T01–T10.

## Device constraint
Planning is being done on Android. The target execution device is a future laptop. Do not assume desktop instructions work on Android/Termux.

## Next actions
1. Complete line-by-line review of both upstream installer scripts and update mechanism; inspect any downloaded scripts before execution.
2. Review recent upstream releases/commits, security posture, and dependencies.
3. Verify NVIDIA model endpoint compatibility, account-specific quota/rate limits, billing behavior, and data terms. Do not add a payment method or enable paid usage without explicit approval.
4. After laptop purchase, record model, OS/version, CPU architecture, RAM, disk space, administrator access, and network reliability.
5. Install only after the preceding gates are documented.
6. Test in a disposable workspace and record evidence before allowing any production-repository access.

## Status rule
Only mark PASS when reproducible evidence is recorded. Use PASS / FAIL / UNTESTED / BLOCKED. No secrets in this public repository.


## Follow-up audit — FCC-PLAN-003 (2026-10-16)

### Files reviewed in upstream
- `scripts/update/fcc-update`: checks the latest published version via `_fcc-update-check`, validates a numeric version, downloads `scripts/install.sh` from a version-tag URL, and executes it. This is better than using `main` for this update path, but the downloaded installer is still executed without a separate checksum/signature verification in this wrapper.
- `scripts/update/fcc-update.cmd`: uses a PowerShell update path and downloads the installer from the selected version tag; separate full review still required.
- `src/free_claude_code/updater/check.py`: queries PyPI metadata over HTTPS and validates the version format and available release file. This check does not itself prove the downloaded installer is signed or hash-verified.
- `.github/workflows/tests.yml`: the inspected CI workflow uses pull-request triggers and `contents: read` permissions in the reviewed jobs. This is a positive control for those jobs only; it is not a full audit of every workflow.
- `src/free_claude_code/api/routes.py`: inspected initial section; this alone does not settle whether request content is logged elsewhere. Check logging configuration and server logs before using private code.

### Risk decision
- **BLOCKED for installation for now**: installer/update chain not fully audited end-to-end, OS compatibility unknown, and no disposable-device test has run.
- Do not interpret this as a finding that FCC is malicious. It is a risk-control decision until the remaining checks are completed.
- Do not send private MR.ONE source, production credentials, or sensitive prompts through the proxy until logging and provider data-handling terms are verified.

### NVIDIA access finding
- NVIDIA's official documentation says Developer Program members can access hosted NIM API endpoints for prototyping; model availability and account entitlement still need to be checked in the signed-in account. No key has been created or tested here and no paid usage was initiated.
- Exact free quota, rate limits, reset behavior, card requirements, and account eligibility remain **UNTESTED** for Iwan's account.

### Next actions
1. Audit the complete install scripts, updater scripts, and any scripts downloaded by them, with emphasis on checksums/signatures, profile/PATH edits, persistence, privilege escalation, and uninstall behavior.
2. Review all workflows and the full request/logging path, including whether prompts are written to local files.
3. Select a pinned release only after compatibility and supply-chain checks; never run a remote script piped directly to a shell as the first test.
4. Revisit the NVIDIA account-specific free access, limits, and terms before any API test.
