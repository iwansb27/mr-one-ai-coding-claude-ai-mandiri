# Installation Plan — Not Yet Executable

**Status:** BLOCKED until target laptop and upstream compatibility are known.

## Gate 0 — Device details
After the laptop is available, record:
- Manufacturer and model
- OS edition and version
- CPU architecture
- RAM and available disk space
- Administrator access
- Internet reliability

Do not assume the desktop workflow is supported on Android/Termux.

## Gate 1 — Upstream review
- Open https://github.com/Alishahryar1/free-claude-code and its README.
- Confirm owner, license, recent commits/releases, dependencies, issues, and security posture.
- Read all installer scripts before running them.
- Verify OS support and exact installation steps from current upstream documentation.
- Prefer a pinned release or reviewed commit where practical.

## Gate 2 — Provider and cost
- Confirm exact model/provider and API endpoint compatibility.
- Record current free quota, rate limits, model availability, account/card requirements, expiration, data terms, and billing behavior.
- No paid usage or billing activation without explicit approval.

## Gate 3 — Isolated installation
Only after Gates 0–2 pass:
- Back up relevant configuration.
- Use a disposable workspace and least-privilege credentials.
- Record exact commands, versions, exit codes, and sanitized output.
- Do not use production MR.ONE repositories.

## Gate 4 — Acceptance testing
Run T01–T10 from TEST-LOG.md. If a security, compatibility, or billing gate fails, stop and document FAIL or BLOCKED.

## Recovery
Before installation, record uninstall steps and how to restore changed shell/profile/configuration files. Do not proceed without a rollback path.
