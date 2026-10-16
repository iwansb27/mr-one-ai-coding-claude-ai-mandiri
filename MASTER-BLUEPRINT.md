# MR.ONE — Free AI Coding Environment
## MASTER BLUEPRINT / HANDOFF
**Status:** DRAFT — READY FOR REPOSITORY REVIEW  
**Owner:** Iwan  
**Purpose:** Preserve the plan and implementation logic until a laptop is available.  
**Rule:** Documentation is not proof of installation. No component is marked PASS until tested on the target device.

---

## 1. Executive summary

The video demonstrates a workflow built around **Free Claude Code (FCC)**, a GitHub-hosted project intended to provide a free/low-cost Claude Code-style coding environment, and an NVIDIA API key used to access a hosted AI model. The video shows a GitHub README with install commands, then an NVIDIA API-key screen.

The video appears to reference this repository:

- Video repository shown on screen: https://github.com/Alishahryar1/free-claude-code
- Repository README: https://github.com/Alishahryar1/free-claude-code#readme
- NVIDIA API key portal shown in the video: https://build.nvidia.com/settings/api-keys

**Important:** Repository ownership, current maintenance, release status, exact dependencies, install scripts, model compatibility, and NVIDIA usage limits must be re-checked before execution. Do not blindly paste commands from a video. The project is third-party software and is not an official Anthropic product unless its upstream documentation explicitly establishes otherwise.

## 2. Goal and non-goals

### Goals
1. Prepare a reproducible coding-assistant environment for a future laptop.
2. Prefer free tiers and open-source components where practical.
3. Preserve all decisions, setup steps, test evidence, and recovery instructions in GitHub.
4. Make the environment useful for MR.ONE work: code review, debugging, documentation, prototypes, and repository maintenance.
5. Keep API credentials out of Git history and screenshots.

### Non-goals for this planning phase
- Do not install or execute anything on Iwan's Android phone as if it were a supported desktop setup.
- Do not pay for subscriptions, credits, or API usage without explicit approval.
- Do not assume “free” means unlimited or permanently free.
- Do not connect production repositories or run destructive commands before a controlled test.
- Do not claim success without recorded test evidence.

## 3. High-level architecture

```text
Laptop (future target device)
  ├─ Supported operating system (to be selected after laptop purchase)
  ├─ Terminal / shell
  ├─ Git + GitHub account
  ├─ FCC project (third-party installer/application)
  ├─ Claude Code-compatible coding-agent component (exact install method to verify)
  ├─ Model provider configuration
  │    └─ NVIDIA NIM / NVIDIA-hosted model API (network access; API key required)
  └─ Project workspace
       ├─ MR.ONE repositories (one at a time, least privilege)
       ├─ test/sandbox repository
       └─ logs, notes, and checkpoints (never secrets)
```

### Local versus cloud
- The terminal, FCC application, and checked-out code may run locally on the laptop.
- When configured for NVIDIA-hosted inference, the model runs remotely; prompts/code snippets sent to the provider may leave the device.
- This is **not automatically an offline/local AI model**.
- A fully local model is a separate architecture requiring compatible software and sufficient device resources; it is out of scope until assessed.

## 4. Components and purpose

| Component | Purpose | Current status | Verification required |
|---|---|---|---|
| GitHub repository for this blueprint | Durable source of truth | PLANNED | Create repository and commit this document |
| FCC (`Alishahryar1/free-claude-code`) | Main project shown in video | UNTESTED | Inspect README, license, recent commits, releases, issues, scripts, and security posture |
| Git | Version control | PLANNED | Install and verify `git --version` on laptop |
| Supported shell/terminal | Run setup and development commands | PLANNED | Confirm supported OS and shell in upstream docs |
| Claude Code-compatible component | Coding-agent interface/runtime | UNTESTED | Confirm exact installation, version, and compatibility from upstream docs |
| NVIDIA NIM / NVIDIA API key | Hosted model access | UNTESTED | Confirm account eligibility, available models, free quota/rate limits, terms, and endpoint compatibility |
| Network connection | Download packages and call hosted model | REQUIRED | Test reliable internet |
| Secret storage | Protect API key | REQUIRED | Use environment variables or approved secret manager; never commit keys |
| Test repository | Safe validation target | PLANNED | Use a disposable, non-production repository first |
| Laptop | Intended main execution device | NOT YET AVAILABLE | Record model, RAM, storage, OS, and architecture after purchase |

## 5. Workflow inferred from the video

1. Open the FCC GitHub repository.
2. Read the README and locate the install instructions.
3. Review the install script before executing it.
4. Install FCC only on a supported computer/OS.
5. Create an NVIDIA API key using NVIDIA's official portal, if the chosen model/provider setup requires it.
6. Store the key securely in the configuration method documented by FCC. Do not paste it into source files, GitHub issues, chat, or public screenshots.
7. Configure the supported model/provider and endpoint according to the current upstream documentation.
8. Launch FCC and confirm it can reach the model.
9. Run a harmless test in a disposable directory, such as asking the tool to explain a small text file.
10. Record versions, exact commands, outputs with secrets removed, and pass/fail status in the repository.

The video is short and does not establish that every step succeeded, that the configuration remains current, or that the free quota is unlimited.

## 6. Security review gate — mandatory before installation

- Inspect the repository owner, license, commit history, releases, open issues, and README.
- Read install scripts (`install.sh`, PowerShell scripts, or equivalent) before running them.
- Prefer pinned releases or reviewed commits over an unpinned `main` branch installer when practical.
- Do not run commands requiring administrator/root privileges unless justified and understood.
- Never upload `.env`, API keys, cookies, SSH private keys, access tokens, or personal files.
- Use a dedicated test directory and a non-production repository first.
- Review requested permissions before granting GitHub access.
- Treat AI-generated shell commands as suggestions; inspect before execution.
- Keep backups and ensure changes can be reverted.
- If the tool requests broad access to MR.ONE repositories, start with a disposable repository and grant minimum access.

## 7. Cost and free-tier policy

Before choosing a provider, record:
- Is an account required?
- Is identity, phone, or payment-card verification required?
- What is included in the free tier today?
- Are there rate limits, token limits, model availability restrictions, or expiration dates?
- Does a quota reset, and when?
- What happens when the free quota is exhausted?
- Is a payment method required or can charges occur automatically?
- What data may be retained or used by the provider?

**Default decision:** no paid usage and no billing activation without Iwan's explicit approval. A free API key does not guarantee unlimited access or permanent free use.

## 8. Device decision

### Current device
- Android phone only.
- Planning and documentation can be done from the phone.
- The video shows desktop-oriented installation steps. Do not assume that the same commands are supported in Android/Termux.

### Future laptop
After purchase, capture:
- Brand and model
- Operating system and version
- CPU architecture
- RAM
- Free disk space
- Whether the user has administrator access
- Internet reliability

Then choose the supported installation route from upstream documentation. Do not choose minimum hardware requirements until current dependencies have been checked.

## 9. Acceptance tests

A component only becomes PASS when the test result is recorded.

| ID | Test | PASS evidence |
|---|---|---|
| T01 | Upstream project reviewed | Repository URL, license, review date, commit/release inspected |
| T02 | OS support confirmed | Official project documentation explicitly supports the laptop OS |
| T03 | Install completed | Exit status and version output recorded; secrets removed |
| T04 | Provider authentication works | Harmless request receives a valid model response |
| T05 | Cost guard confirmed | Current quota/limits documented; no unexpected billing |
| T06 | Safe workspace works | Tool reads/edits a disposable test file as expected |
| T07 | Git safety confirmed | No secrets in `git status`, tracked files, or commit history |
| T08 | Recovery documented | Uninstall/rollback steps and backup location recorded |
| T09 | MR.ONE use approved | Access scope reviewed and tested on a non-production repo |
| T10 | Handoff complete | Fresh session can resume from this blueprint and checkpoint |

Allowed statuses: **PASS / FAIL / UNTESTED / BLOCKED**. Each test entry should include date, evidence, and next action.

## 10. Proposed repository structure

```text
mr-one-free-ai-coding-blueprint/
├── README.md
├── MASTER-BLUEPRINT.md
├── CHECKPOINT.md
├── COMPONENTS.md
├── SECURITY.md
├── COST-AND-FREE-TIER.md
├── INSTALLATION-PLAN.md
├── TEST-LOG.md
├── DECISIONS.md
└── .gitignore
```

### File responsibilities
- `README.md`: short entry point, goal, status, and links.
- `MASTER-BLUEPRINT.md`: this full plan.
- `CHECKPOINT.md`: exact next step and current blockers.
- `COMPONENTS.md`: component inventory and compatibility.
- `SECURITY.md`: secret handling, permission limits, and review gates.
- `COST-AND-FREE-TIER.md`: dated pricing/quota evidence.
- `INSTALLATION-PLAN.md`: device-specific commands, written only after support is verified.
- `TEST-LOG.md`: evidence-based test outcomes.
- `DECISIONS.md`: locked decisions and reasons.
- `.gitignore`: excludes secrets, environment files, logs containing sensitive data, and local configuration.

## 11. Locked decisions

1. **Documentation first; installation later.**
2. **Laptop is the target environment.** Android is for planning and repository maintenance unless a supported mobile route is separately validated.
3. **Free-first, not free-at-any-cost.** Security and reliability take priority over an untrusted installer.
4. **No secrets in GitHub.**
5. **No production repository access until the sandbox test passes.**
6. **No claim of successful setup without evidence.**
7. **Upstream instructions must be re-checked on the actual installation date.**
8. **This blueprint is a handoff artifact, not proof that FCC or NVIDIA configuration currently works.**

## 12. Current checkpoint

**Checkpoint ID:** FCC-PLAN-001  
**Status:** UNTESTED / PLANNING  
**Completed:** Video workflow summarized; components and validation gates documented.  
**Not completed:** Current upstream audit, OS compatibility verification, installation, API authentication, runtime test.  
**Blocker:** Laptop not yet available.  
**Repository:** https://github.com/iwansb27/mr-one-ai-coding-claude-ai-mandiri (public).  
**Next action:** Review upstream FCC project and current provider terms; then confirm target laptop OS/hardware when available. Do not install or run FCC yet.

## 13. Official and upstream links to re-check

- FCC repository shown in video: https://github.com/Alishahryar1/free-claude-code
- FCC README: https://github.com/Alishahryar1/free-claude-code#readme
- NVIDIA API keys: https://build.nvidia.com/settings/api-keys
- NVIDIA model catalog and current terms: https://build.nvidia.com/
- GitHub documentation: https://docs.github.com/

**Review note:** Links are recorded as research starting points. Confirm they remain correct, current, and trustworthy at the time of installation.