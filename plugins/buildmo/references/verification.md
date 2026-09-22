# Verification and live handoff

Use the current root `AGENTS.md`, `DOMAIN-MAP.md`, package scripts, and CI
workflow to choose checks. Command names in this file are examples of the
current repository interface, not permission to ignore newer repository rules.

## During implementation

- For a bug, reproduce the failure before changing code when practical.
- Add or extend the smallest regression test that detects the original failure.
- Run focused tests after each meaningful correction.
- Pair isolated tests with a small real journey through collaborating parts.
- Use production logic inside the tested boundary and mock only outside it.
- If repeated repairs add exceptions or duplication, stop and replace the
  faulty approach rather than stacking another patch.

## Before the user judges the slice

Run focused checks with a credible chance of exposing the change. Report exact
commands, duration, result, first failing layer, mocked or untested boundaries,
and a copy-paste rerun command. A skipped, stale, interrupted, or blocked check
is not green.

Start or reuse the worktree's estate only when the user needs to try the
feature or live evidence is required. Use `npm run dev:status` for the serving
worktree, branch, commit, and dynamic URLs. Never assume ports. Preserve an
existing estate unless replacement is requested or necessary and authorized.

Give the exact route, starting state, actions, and expected result. Screenshots
support visual judgement; they do not replace a usable live build. For
non-visual work, provide the real trace, output, or deterministic scenario.

## Submission preparation

After the behaviour is accepted, run the handoff lanes selected by current
repository policy. This may include `npm run verify:changed:background`, the
owning `verify:domain` command, `npm run verify:all`, affected journeys, and the
push guards. Do not run broad unchanged suites merely for ceremony when hosted
CI owns them, and do not claim a journey ran without checking the selector.

Report a background lane's exact status and log path without holding the user
turn open unnecessarily. Hosted CI is authoritative for its required checks.
