---
name: spec
description: "Create or revise an implementation-ready BrainMo design specification in Guru’s maintained docs/design-specs system. Use for ‘Spec it’ after a direction is chosen. Keeps behaviour with the designer, obeys DESIGN.md and design guardrails, and stops for approval before implementation."
---

# Spec

Create the product truth that implementation, critique, and QA will use.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/design-authority.md`, and `../../references/state.md` first.

## Open

- Read the feature state and chosen framing.
- Resolve or create the feature worktree under current repository rules. A
  specification is a repository change; do not write it in the coordination
  checkout.
- Read root `AGENTS.md`, `DESIGN.md` completely, `DOMAIN-MAP.md`, and the
  nearest nested instructions.
- Read `docs/design-specs/README.md`, guardrails, the appropriate template,
  the writing-style guide, the index, at least two relevant goldens, and every
  specification this feature depends on one level deeper.
- Read the component map and the relevant foundation, component, interaction,
  behaviour, and animation documents.

## Write

- Extend an owning specification when one already exists; do not create a
  competing source of truth.
- Use the repository's template and nearest goldens. Remove guidance,
  placeholders, examples, and irrelevant sections.
- Describe what the system must do, not implementation mechanics.
- Use British spelling, short bullets, exact values, and `must`/`must not` for
  behaviour rules.
- Preserve the required heading hierarchy and dependency filename format.
- Put UI copy in the location required by the current writing guide.
- Reference existing components and patterns. Stop if a genuinely new global
  component or pattern needs a product decision.
- Do not invent behaviour. Use a clearly owned `(TBD)` while drafting, but do
  not call the specification handoff-ready until every remaining TBD is
  resolved or explicitly accepted and logged.
- Keep Future Considerations outside implementation scope.

## Verify

Check the specification against the current template, goldens, guardrails,
related specifications, component map, `DESIGN.md`, dependency paths, exact
copy, edge/failure states, unnecessary repetition, vague design-owned values,
and remaining TBDs. Run any repository-provided spec validation relevant to the
changed files.

Record the path, checks, interpretations, and open decisions in the feature
state. Do not implement product code.

End with:

1. Spec is right — build it.
2. Revise the named sections.
3. Resolve the listed product decisions first.

Waiting on you.
