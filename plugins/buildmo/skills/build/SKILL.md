---
name: build
description: "Implement the smallest coherent, reviewable BrainMo/Guru slice in the correct worktree, verify it proportionally, run or reuse the local estate, and give the user an exact live scenario to judge. Use for ‘Build it’, ‘implement this’, or an approved fix. Do not use for read-only investigation, critique, QA, commit, push, pull request, review-room deployment, or merge."
---

# Build

Make one real outcome work and put it in the user's hands. Nothing leaves the
machine in this stage.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/state.md`, and `../../references/verification.md` first. Read
`../../references/security.md` when its boundary applies.

For any UI, visual, interaction, or user-facing copy change, read root
`DESIGN.md` completely and `../../references/design-authority.md` before
planning or editing. Say explicitly that current `DESIGN.md` governs the UI.

## Open

- Read the feature state, approved specification when present, and any accepted
  investigation. If there is no spec, say so once and do not pretend one exists.
- Resolve the designated worktree and branch using the repository protocol.
- Run setup checking, read `DOMAIN-MAP.md`, nested instructions, owning code,
  callers, existing tests, and nearby maintained comments.
- Check the worktree for existing changes. Preserve them; identify overlap
  before editing.
- State the six-line contract. Add a short Evidence line when traces,
  transcripts, screenshots, or production behaviour determine the change.

Implementation details that do not affect the experience are yours to decide.
When two plausible readings produce meaningfully different teacher behaviour,
present at most three options, recommend one, and stop. An explicit request to
ask before proceeding overrides the default bias to build.

## Slice

Choose the smallest independently judgeable outcome, not mechanically the first
file or first item in a list. A coherent slice may cross UI, server, shared
contract, prompt, and tests when all are required for one real behaviour.

Prefer an outcome the user can try. Do not build architecture with no observable
result unless it is a deliberately approved enabling slice. Record everything
left for later.

## Implement

- Reuse existing components, policies, stores, services, and test journeys.
- Stay inside the intended domain boundary.
- Preserve exact approved copy and all applicable states.
- Find and migrate every caller when a contract changes.
- Keep ChatMo evidence teacher-scoped and bounded before provider calls;
  mutation targets come only from trusted editable context.
- Classify new background triggers for review-room safety.
- Do not add a dependency without naming the package, version, and why the
  platform or existing dependencies cannot do the job.
- Do not change external prompts or configuration merely because local code
  expects a later publication step.

## Verify and show

Follow the focused development and live handoff rules in
`../../references/verification.md`. For a bug, retain evidence that the new
regression test detects the original failure when practical.

Run or reuse the worktree estate only as needed. Confirm the serving worktree,
branch, and commit with the repository status command. Give the user the
dynamic URL, exact route, starting state, steps, and expected result. Preserve
other estates and test data.

Append the worktree, slice, assumptions, evidence, commands/results, serving
commit, and deliberate omissions to BuildMo state and the owning domain worklog
when required.

Do not commit, push, open a pull request, deploy a review room, publish external
configuration, or continue automatically into Critique.

End with:

1. Looks right — critique it.
2. Adjust the named details in this worktree.
3. Skip critique — QA it.
4. Stop here.

Waiting on you.
