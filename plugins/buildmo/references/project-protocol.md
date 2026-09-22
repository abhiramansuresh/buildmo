# Guru project protocol

Read this before any BuildMo stage that inspects or changes Guru.

## Authority

The current repository owns its changing truth. Read instructions from disk;
do not rely on a copy in this plugin.

1. Platform, user, and machine-local instructions.
2. Root `AGENTS.md` and the nearest nested `AGENTS.md`.
3. `docs/design-specs/design-guardrails.md` and the owning feature/component
   specification for product behaviour.
4. Root `DESIGN.md` for current visual identity and interaction summary.
5. `DOMAIN-MAP.md` for ownership, boundaries, and canonical verification.
6. Code and tests for executable truth.
7. BuildMo for stage sequencing.

If BuildMo conflicts with a higher source, follow the higher source and record
the mismatch. Do not copy changing tokens, branch lists, commands, or room
details into the skill when the repository already maintains them.

## First minute

- Find the repository root.
- Read root `AGENTS.md`.
- Run `npm run setup:check` when the stage will execute repository commands or
  change files.
- Read `DOMAIN-MAP.md` and the nearest nested `AGENTS.md` for the owning area.
- Read the feature's BuildMo state, if one exists.
- State the six-line contract before implementation: outcome, invariant,
  non-goals, verification, intended diff boundary, and rollback/escalation.

## Worktrees

The primary checkout is coordination-only. Do not switch its branch, stage
product files, or run task-local generators there.

Resolve the worktree in this order:

1. Reuse the worktree recorded in the feature state.
2. Obey a machine-local or project instruction that assigns the domain to a
   persistent shared worktree and branch.
3. Otherwise fetch current `origin/staging`, create a short-lived branch from
   it, and create a dedicated worktree.

Do not create a replacement for an existing designated worktree. Copy ignored
`.dev.vars` files from the primary checkout when repository instructions require
them. Never print, stage, or commit their values.

Preserve unrelated changes and every other running Guru estate. If an existing
change overlaps the requested work, identify its owner and intent from status,
state, and work logs before editing.

## Scope and risk

- Stay within one `DOMAIN-MAP.md` owner plus explicit contract/shared-test
  files unless the behaviour requires a cross-domain contract change.
- A request/response shape change requires every caller to be found and
  migrated or deleted in the same change.
- New autonomous triggers must be classified under the review-room background
  work contract before implementation.
- Do not run Prisma migrations without explicit approval.
- Do not mutate PostHog, cloud configuration, review rooms, deployments, or
  production as an implied part of local implementation.
- Never weaken, skip, or delete a valid test to make a check pass.

## Git and integration

- `staging` is the ordinary integration branch. Feature branches never target
  `main`.
- Unstacked feature branches rebase onto current `origin/staging`; do not merge
  `staging` into them.
- Preserve stack ancestry for stacked pull requests.
- Promotion from `staging` to `main` and history reconciliation use merge
  commits and the exact procedure in `.github/README.md`.
- Commit, push, pull request, merge, migration, review-room mutation, and cloud
  actions each require explicit authority naming that action.
