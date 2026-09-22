---
name: review-room
description: "Put an explicitly authorized Guru candidate into a shared BrainMo review room, verify the deployed environment, record review evidence, and safely reset and release the room afterward. Use for ‘put this in a review room’, shared designer review, room status, reseed, placement, reset, or release. Every room mutation requires explicit authority."
---

# Review Room

Operate Guru's shared review environments without confusing a deployed frontend
with a ready room or leaving a dirty room available to someone else.

Read `../../references/voice.md`, `../../references/project-protocol.md`,
`../../references/state.md`, and `../../references/review-rooms.md`. Then read
the current `docs/development/REVIEW-ROOMS.md` completely before acting.

## Establish authority

Identify the exact requested action: inspect, claim, push candidate, reseed,
change placement/provider, test, reset, or release. Read-only inspection needs
no additional authority. Each mutation must be named by the user; one does not
imply the others.

Before a push, report the candidate branch, commit, staging base, verification,
room, topic, collaborators, and any database/location choice. If a missing
choice changes authentication or replaces data, stop for the decision.

## Operate

Follow the current repository guide and supported Main Road or MCP interfaces.
Never improvise provider steps from memory. Use the documented lease-protected
push. Wait for all required deployment and health evidence before calling the
room ready.

For reseed or provider changes, state what data will be replaced and confirm
the exact room. Never expose credentials. Record the room, deployed commit,
stable links, database/auth mode, checks, and lease state in BuildMo state.

## Close safely

Do not release a room merely because review is finished. After the candidate
has entered staging through the normal path, reset the room branch to current
staging, wait for deployment and backend health, then release only if that
release was authorized. Leave a failed reset claimed.

End with only the decisions that actually remain, for example:

1. Review this deployed candidate now.
2. Reseed this room's isolated data.
3. After staging merge, reset and release the room.

Waiting on you.
