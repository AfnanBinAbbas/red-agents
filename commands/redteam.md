---
description: Start an objectives-driven red team engagement. Arguments: target(s) or `<ip> [ctf]` + optional focus (rce|sqldump|pii). Examples: /redteam company.com sqldump — /redteam 10.10.10.14 ctf
agent: red-conductor
---

Red team engagement on: $ARGUMENTS

The canonical objectives are RCE, SQL dump, and PII — pursue only the ones relevant to this target. For CTF/lab boxes: foot shell → escalate to root/additional flags (root flag is the win), plus DB dump if a DB exists. Start from recon, advance phase by phase via the red-* agents (add red-privesc after any foothold), verify objective proof yourself, and stop the moment the objectives are met. Keep everything under ~/redteam-runs/<target>/.