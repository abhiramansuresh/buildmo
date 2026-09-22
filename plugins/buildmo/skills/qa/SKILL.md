---
name: qa
description: "Perform design and journey QA on a running BrainMo/Guru slice using real captured evidence, current DESIGN.md, the approved specification, dynamic worktree URLs, and safe test-data cleanup. Use for ‘QA it’, staging QA, or acceptance evidence. Report findings; do not silently implement fixes or mutate shared environments without authority."
---

# QA

Prove what the built experience actually does. Automated checks support this
stage; they do not replace seeing and using the real state.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/state.md`, and `../../references/verification.md`. For UI
work, read root `DESIGN.md` completely and
`../../references/design-authority.md`.

If QA uses a shared review environment, also read
`../../references/review-rooms.md` and the current repository review-room guide.
Do not claim, reseed, push, reset, or release a room unless that exact action is
authorized.

## Prepare

- Confirm the exact environment, branch, and commit being tested.
- Read the approved spec, BuildMo state, prior critique, and previous QA
  evidence for this slice.
- Define the journeys and states before acting, including cleanup.
- Use anonymised or deterministic test data. Do not expose production personal
  information in screenshots or reports.

## Exercise

- Walk each journey as the teacher would, including meaningful transitions and
  affected extended journeys.
- Test the important states and the relevant edge/failure conditions.
- Capture the source visual truth, viewport, density, route, starting state,
  actions, result, console/network errors, and implementation screenshot where
  visual comparison matters.
- Use focused-region comparisons for small visual differences.
- Record workarounds explicitly. A flow that passes only after a workaround is
  not an ordinary pass.
- Confirm saved state after reload when persistence matters.
- Undo or remove test mutations when safe; record anything that could not be
  restored.

Store evidence in `.guru/qa/<date>-<slug>/design-qa.md` in the coordination
checkout, with screenshots beside it. Mark each journey passed, failed, or
blocked and state the precise evidence. A visual pass requires actual visual
inspection; a green test suite is not visual evidence.

Do not fix findings in QA. Append the result to BuildMo state.

End with:

1. QA is clean — prepare to ship.
2. Return to Build for the named failures.
3. Accept the named blocker and continue.
4. Stop with the QA evidence.

Waiting on you.
