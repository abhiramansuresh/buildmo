---
name: investigate
description: "Diagnose a BrainMo/Guru bug, confusing behaviour, transcript, trace, or implementation question without changing product code. Use for ‘Investigate it’, ‘diagnose’, ‘why is this happening’, ‘look and report’, or explicit no-implementation requests. Produces evidence, root cause, impact, and a bounded fix recommendation."
---

# Investigate

Explain what is happening and why. Do not implement the fix unless the user
later starts Build.

Read `../../references/voice.md`, `../../references/project-protocol.md`, and
`../../references/state.md` first. Read `../../references/security.md` when
production traces, accounts, prompts, or user data are involved.

## Evidence

- Read the report, screenshots, transcripts, traces, Asana context, Backdoor
  diagnostics, specifications, code, tests, and recent changes actually placed
  in scope.
- Work from the branch or persistent worktree that owns the reported behaviour.
  Do not silently compare the wrong checkout with production or staging.
- Separate observed facts from inference. Correlate identifiers and timestamps
  without exposing personal data or secrets.
- Reproduce locally or through a safe read-only path when practical.
- Trace ownership across UI, server, model prompt, deterministic policy,
  persistence, external configuration, and deployment before labelling the
  cause.

## Report

Lead with the cause, not the search history:

- **What the person experiences.**
- **Where the failure begins.**
- **Why it happens.**
- **Evidence.** The concrete trace, code path, test, or reproduction.
- **Blast radius.** Which journeys are affected and which are not.
- **Fix shape.** The smallest root-cause correction and regression coverage.
- **Unknown or unverified boundaries.**

Do not edit product files, tests, prompts, external systems, tickets, or cloud
state. Recording the read-only result in ignored BuildMo state is allowed.

End with:

1. Build the recommended fix.
2. Investigate the named uncertainty further.
3. Stop with this report.

Waiting on you.
