# MR.ONE Claude AI Coding Mandiri

**Owner:** Iwan  
**System:** MR.ONE  
**Checkpoint:** FCC-PLAN-001  
**Status:** UNTESTED / PLANNING  
**Repository visibility:** Public

## Purpose

This repository is the public planning and handoff source for MR.ONE's Claude-style AI coding environment and the longer-term autonomous-agent direction. It records architecture, security gates, free-tier checks, device-specific installation planning, and evidence-based tests.

## Current scope

- Prepare documentation on Android.
- Target actual installation on a future laptop after its operating system and hardware are known.
- Evaluate Free Claude Code (FCC) as a third-party candidate, not an official Anthropic product.
- Evaluate NVIDIA-hosted model access only after checking current compatibility, quota, terms, and billing risk.
- Keep this coding-environment project separate from the broader MR.ONE Autonomous Cloud Agent blueprint.

## Current status

Planning only. No installation, provider authentication, or runtime test is claimed as complete. Do not treat a plan as proof of working software.

## Document index

- [Master Blueprint](MASTER-BLUEPRINT.md)
- [Checkpoint](CHECKPOINT.md)
- [Components](COMPONENTS.md)
- [Security](SECURITY.md)
- [Cost and Free Tier](COST-AND-FREE-TIER.md)
- [Installation Plan](INSTALLATION-PLAN.md)
- [Test Log](TEST-LOG.md)
- [Decisions](DECISIONS.md)

## Upstream research starting points

- [Free Claude Code repository](https://github.com/Alishahryar1/free-claude-code)
- [FCC README](https://github.com/Alishahryar1/free-claude-code#readme)
- [NVIDIA API keys](https://build.nvidia.com/settings/api-keys)
- [NVIDIA model catalog](https://build.nvidia.com/)

Re-check upstream ownership, license, releases, scripts, compatibility, quota, and terms before use.

## Safety rules

1. Never commit API keys, tokens, passwords, cookies, SSH private keys, or personal files.
2. Never run an unreviewed remote installer blindly.
3. Do not activate paid billing or incur paid usage without Iwan's explicit approval.
4. Test in a disposable workspace before granting access to production repositories.
5. Mark a test PASS only when real evidence is recorded.
6. Public visibility means anyone can read the repository. Do not store private operational details or secrets here.

## Status vocabulary

PASS / FAIL / UNTESTED / BLOCKED
