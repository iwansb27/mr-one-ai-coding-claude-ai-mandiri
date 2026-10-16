# Component Inventory

| ID | Component | Purpose | Status | Required verification |
|---|---|---|---|---|
| C01 | This GitHub repository | Public blueprint and handoff | PASS — repository found; README committed | Confirm all expected files are present |
| C02 | Free Claude Code (FCC) | Third-party coding environment shown in the reference workflow | UNTESTED | Review owner, license, commits/releases, dependencies, installer and security posture |
| C03 | Git | Version control | PLANNED | Verify version on target laptop |
| C04 | Shell/terminal | Run commands and coding workflow | PLANNED | Confirm OS/shell support upstream |
| C05 | Laptop OS and hardware | Execution environment | BLOCKED — laptop not yet available | Record model, OS, CPU architecture, RAM and storage |
| C06 | Coding-agent runtime | Agent interface and tool execution | UNTESTED | Confirm exact component, version and compatibility |
| C07 | Hosted model provider (NVIDIA candidate) | Model inference | UNTESTED | Confirm models, endpoint compatibility, quota, terms and billing |
| C08 | API key / secret storage | Authenticate without exposing credentials | REQUIRED | Use environment variable or approved secret manager; never commit secrets |
| C09 | Network | Downloads and hosted inference | REQUIRED | Verify reliability on laptop |
| C10 | Disposable sandbox repository | Safe initial tests | PLANNED | No production data; least privilege |
| C11 | Test log and checkpoints | Evidence and handoff | PLANNED | Record commands/output with secrets removed |
| C12 | Future MR.ONE integration | Use agent on MR.ONE work | BLOCKED pending sandbox PASS | Start with non-production repo and minimal permissions |

## Architecture boundary
FCC is a candidate component, not the complete MR.ONE Autonomous Cloud Agent. A hosted model means prompts/code may leave the device. A fully local model is a separate architecture and is not assumed here.
