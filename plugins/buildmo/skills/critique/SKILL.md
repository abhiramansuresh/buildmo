---
name: critique
description: "Run an adversarial, read-only critique of a built BrainMo/Guru slice against its approved specification, current DESIGN.md, design system, copy, edge cases, accessibility, persistence, security, review-room safety, and code health. Use for ‘Critique it’ or ‘tear it apart’. Find and rank issues; do not fix them."
---

# Critique

Find what is wrong. Do not confirm the work and do not fix anything in this
stage.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/state.md`, and the feature state. For UI work, read current
root `DESIGN.md` completely and `../../references/design-authority.md`. Read
`../../references/security.md` when applicable.

## Passes

Run every applicable pass and name those skipped:

1. **Intent and specification:** every requirement, entry point, flow, exit,
   constraint, edge case, and deliberate non-goal.
2. **Current DESIGN.md:** visual character, canvas, tokens, typography,
   spacing, depth, shape, motion, layering, shared helpers, and prohibited
   patterns.
3. **Design-system ownership:** component map, component specifications,
   interaction patterns, behaviour patterns, reuse, and unapproved variants.
4. **Teacher-facing copy:** exact approved wording, clarity, actionability, and
   product voice.
5. **Interaction and recovery:** feedback, exits, undo, destructive actions,
   precision the system could infer, loading, empty, error, one, many, long,
   offline, slow, denied, concurrent, refresh, and navigation.
6. **Accessibility:** keyboard order, focus, contrast, labels, roles, target
   size, reading order, and reduced motion.
7. **State and persistence:** reload, back, second tab, stale response,
   retry/idempotency, and impossible state combinations.
8. **Security and privacy:** authorization, boundaries, disclosure, secrets,
   and pupil/teacher scope.
9. **Review-room safety:** any autonomous trigger is gated or explicitly
   classified under the current repository inventory.
10. **Code health:** duplicated policy, swallowed errors, speculative
   abstraction, one-off component variants, and dependencies added for trivial
   work.

## Findings

- **P0:** the person cannot complete the flow, data is lost/corrupted, or a
  security boundary fails.
- **P1:** behaviour contradicts the approved experience, design system, or a
  reasonable expectation.
- **P2:** polish or anything not verified.

Each finding states the effect on the teacher, the exact state or input that
produces it, evidence, and a tight file/line location. State passes with no
findings. Do not edit files, regenerate snapshots, or “clean up” while reviewing.

Append findings to BuildMo state.

End with:

1. Build fixes for P0 and P1; leave P2.
2. Build only the named findings.
3. QA the current result without fixes.
4. Stop with the critique.

Waiting on you.
