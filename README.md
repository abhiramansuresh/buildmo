# BuildMo

BuildMo is BrainMo's design-led delivery workflow for the Guru repository. It
lets designers and product teammates keep control of the experience while an
agent handles repository research, specifications, isolated implementation,
verification, review rooms, and GitHub handoff.

BuildMo does not carry a frozen copy of Guru's product rules. It reads the
current `AGENTS.md`, `DOMAIN-MAP.md`, `DESIGN.md`, owning design specifications,
and review-room documentation from the checked-out Guru repository whenever a
stage needs them.

## Stages

| Command | Result |
| --- | --- |
| `frame` | Problem, evidence, options, and a recommendation. |
| `spec` | An approved design specification in the repository's format. |
| `investigate` | Evidence-backed cause report with no implementation. |
| `build` | The smallest coherent slice, running locally for review. |
| `critique` | Adversarial findings only; no silent fixes. |
| `qa` | Real journey and visual evidence with cleanup recorded. |
| `review-room` | An explicitly authorized shared review deployment. |
| `ship` | Authorized commit, push, pull request, CI, merge, and rollout steps. |
| `status` | Read-only state across in-flight features, worktrees, PRs, and rooms. |

Each stage stops before the next. Product and UX choices stay with the person
using the skill. Commit, push, pull request, merge, migration, review-room
mutation, and cloud actions require explicit authorization.

## Install in Codex

```text
codex plugin marketplace add https://github.com/abhiramansuresh/buildmo
codex plugin add buildmo@buildmo
```

Start a new task after installation. Use `$buildmo:frame`, `$buildmo:spec`,
`$buildmo:investigate`, `$buildmo:build`, `$buildmo:critique`, `$buildmo:qa`,
`$buildmo:review-room`, `$buildmo:ship`, or `$buildmo:status`.

## Install in Claude Code or Cowork

```text
/plugin marketplace add abhiramansuresh/buildmo
/plugin install buildmo@buildmo
```

Use `/buildmo:frame`, `/buildmo:spec`, `/buildmo:investigate`,
`/buildmo:build`, `/buildmo:critique`, `/buildmo:qa`,
`/buildmo:review-room`, `/buildmo:ship`, or `/buildmo:status`.

Because this repository is private, each teammate needs GitHub access to it
before installation.

## Repository layout

```text
.agents/plugins/marketplace.json
.claude-plugin/marketplace.json
plugins/buildmo/
  .codex-plugin/plugin.json
  .claude-plugin/plugin.json
  references/
  skills/
```

## Maintaining BuildMo

Keep changing operational facts in Guru's own maintained documentation. Change
BuildMo when the delivery workflow or decision boundaries change. When releasing
an update, bump the version in both plugin manifests and the Claude marketplace
entry together.
