# red-agents

opencode agent definitions for the objectives-driven red-team pipeline — the AI layer
that drives the 9 deterministic phase repos (`red-conductor`, `red-recon`, `red-survey`,
`red-exploit-web`, `red-exploit-infra`, `red-privesc`, `red-exfil`, `red-validate`,
`red-report`).

## Contents

```
agents/red-conductor.md      orchestrator: drives phases toward objectives, tracks state
agents/red-recon.md          phase 1: OSINT/DNS/exposure only
agents/red-survey.md         phase 2: network scan only (nmap/nuclei/dirbust)
agents/red-exploit-web.md    phase 3a: web vuln classes only
agents/red-exploit-infra.md  phase 3b: infra/service/panel classes only
agents/red-privesc.md        post-foothold escalation
agents/red-exfil.md          objectives: SQL dump / PII / credential recovery
commands/redteam.md          /redteam <target> [ctf] [rce|sqldump|pii]
```

## Install

```bash
mkdir -p ~/.config/opencode/agent ~/.config/opencode/command
cp agents/red-*.md ~/.config/opencode/agent/
cp commands/redteam.md ~/.config/opencode/command/
```

## Rules baked in

- One owner per attack class (see red-ops-doctrine / VULN_INDEX)
- Consume checkpoint files — never re-run another phase's scan
- Objectives only: RCE, SQL dump, PII (or CTF flags); prove impact before claiming
- OPSEC doctrine: quiet by default, loud only when the objective requires it

Authorized targets only.
