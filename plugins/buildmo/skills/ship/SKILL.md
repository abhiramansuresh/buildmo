---
name: ship
description: "Prepare and perform explicitly authorized Git and release actions for a completed Guru slice: submission verification, commit, push, pull request, CI monitoring, merge to staging, rollout monitoring, and separately authorized promotion or cloud changes. Use for ‘Ship it’, commit, push, PR, merge, or deployment requests. Never infer an unmentioned external action."
---

# Ship

Move accepted work through Guru's real integration path without broadening the
authorization.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/state.md`, `../../references/verification.md`, and
`../../references/security.md`. Read current root `AGENTS.md`,
`.github/README.md`, pull-request template, owning nested instructions, feature
state, QA evidence, and domain worklog.

## Authority

List the requested actions: commit, push, open pull request, merge, migration,
external configuration, review-room operation, deployment, or production
promotion. Perform only those explicitly named. If the user already named a
specific set in the current request, that is the checkpoint for that set; do
not ask them to repeat it. An approval for one action does not imply another.

## Prepare

- Confirm the exact worktree, branch, base, and clean ownership of every change.
- Complete the submission checks required by current repository policy. Report
  commands, durations, failures, skipped boundaries, background status, and
  rerun commands.
- Review the full diff, separating semantic changes from generated output,
  lockfiles, snapshots, and mechanical movement.
- Confirm the diff contains no secret, local credential, absolute local path,
  or unrelated user change.
- Confirm the domain boundary and every changed contract caller.
- Fetch current `origin/staging`. Rebase an unstacked branch; preserve stack
  ancestry when dependants exist.
- Update the owning worklog before commit when required.

If authorization is incomplete, present the proposed message, files/lines,
destination, verification, outstanding findings, and exact actions requiring a
yes. Stop.

## Execute authorized actions

- Commit an outcome, not mechanics.
- Push the feature branch, never `staging` or `main` directly.
- Open ordinary feature pull requests to `staging`; follow stack targeting for
  dependent slices.
- Fill the repository template with outcome, invariants, exact evidence, known
  gaps, and intended omissions.
- Monitor required checks to completion. Pending is not passing. Reproduce and
  repair in-scope failures rather than bypassing protection.
- Merge only when explicitly authorized, checks are current and green, and
  conversations are resolved.
- Treat a staging merge and the resulting deployments as separate facts.
  Monitor the relevant Cloudflare and backend rollout before saying a change is
  live.
- Follow the exact ancestry-preserving procedure for `staging` to `main`.

Attach every created pull request to the task when the host supports it.
Record commit, PR, merge, rollout state, and known follow-ons in BuildMo state.

End with the next unperformed decision only. Do not automatically begin the
next slice.

Waiting on you.
