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
