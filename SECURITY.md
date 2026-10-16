# Security Controls

This repository is public. Treat all committed text as visible to anyone.

## Non-negotiable controls
- Never commit API keys, tokens, passwords, cookies, SSH private keys, account recovery codes, or private user data.
- Never place secrets in README files, screenshots, issues, logs, test fixtures, or prompts committed to the repo.
- Review install scripts and dependencies before execution. Do not blindly pipe a remote script to a shell or run unreviewed PowerShell.
- Prefer pinned releases or reviewed commits over unpinned main-branch installers when practical.
- Avoid administrator/root privileges unless the need is justified and understood.
- Use a disposable directory and test repository first.
- Grant the minimum permissions required. Do not grant broad access to production MR.ONE repositories before sandbox acceptance tests pass.
- Inspect AI-generated commands before execution; an agent suggestion is not proof of safety.
- Keep backups and document rollback/uninstall steps.
- Treat hosted-model prompts and code snippets as data that may leave the device; do not send private or production data until provider terms and authorization are reviewed.

## Before each installation
1. Verify upstream repository owner, license, recent commits/releases, dependencies, open issues, and any security policy.
2. Read every installer script and note downloads, privilege escalation, shell/profile changes, network calls, and persistence.
3. Confirm operating-system support from official project documentation.
4. Review requested permissions and secret handling.
5. Confirm free-tier limits and billing behavior before creating/using credentials.

## If a secret is exposed
1. Revoke/rotate the credential at its provider immediately.
2. Remove it from the current file and assess commit history; deleting a file alone does not erase Git history.
3. Review provider usage and repository access logs where available.
4. Record the incident without copying the secret into this public repo.

The .gitignore file is only a secondary control; it does not replace review of staged files or Git history.


## Follow-up audit notes — 2026-10-16
- The updater wrapper reviewed at `scripts/update/fcc-update` downloads the installer from a version-tag URL after checking the latest published version. The wrapper inspected here does not itself verify a cryptographic signature or checksum for the installer payload; verify the full release/download chain before running it.
- The corresponding Windows updater downloads a version-tagged PowerShell installer; it also requires full review before execution.
- The reviewed CI workflow file uses pull-request triggers and `contents: read` on inspected jobs. This is a limited observation, not a complete audit of all workflows or branch protection.
- A historical public issue reports plaintext request payload logging and an earlier CI automation problem. Treat that as a lead to verify against the current commit, not as proof the current version has the same issue: https://github.com/Alishahryar1/free-claude-code/issues/104
- Until logging and provider data handling are confirmed, do not submit private or production MR.ONE code through FCC.
