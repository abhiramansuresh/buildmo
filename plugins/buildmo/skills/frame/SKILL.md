---
name: frame
description: "Frame a BrainMo feature or experience in the Guru repository before code or specification work. Use for ‘Frame it’, rough product ideas, feature direction, or when the team needs evidence-backed options and a recommendation. Do not implement, write a specification, or mutate external state."
---

# Frame

Turn a rough BrainMo idea into a product decision. The user owns the experience;
you assemble the evidence and make the decision easy.

Read `../../references/voice.md`, `../../references/project-protocol.md`, and
`../../references/state.md` first.

## Orient

- Confirm this is the Guru repository. If it is not, explain that BuildMo is
  Guru-specific and stop.
- Read current root `AGENTS.md`, `DOMAIN-MAP.md`, the existing feature state,
  `docs/design-specs/what-is-brainmo.md`, design guardrails, the design-spec
  index, related specifications, and the owning implementation.
- Read relevant research in `.guru/ux-loop/research/<slug>.md` if present. It
  is evidence, not truth.
- Do not search old implementation plans by default. Product truth is in
  maintained specifications; executable truth is in code and tests.

If the idea changes UI, read root `DESIGN.md` completely and then
`../../references/design-authority.md`. BuildMo must use the file's current
contents, not memory or a bundled summary.

## Produce

Keep the framing concise:

- **Problem:** what the teacher is trying to do and where Guru makes it harder.
- **Evidence:** current behaviour, specifications, components, research, and
  unresolved contradictions.
- **What already exists:** the nearest reusable pattern and its limits.
- **Real constraints:** distinguish “cannot” from “would take work”.
- **Options:** at most three; teacher experience, cost, and what each forecloses.
- **Recommendation:** one option and the reason.
- **Unknowns:** facts or product choices the evidence cannot settle.

Do not change repository files. Creating or appending the ignored feature state
is allowed. Record the options, recommendation, evidence, and open questions.

End with a numbered decision such as:

1. Use the recommended direction — spec it.
2. Use another listed direction.
3. Reframe with the correction supplied by the user.

Waiting on you.
