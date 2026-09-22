# Review-room operations

Read the current `docs/development/REVIEW-ROOMS.md` completely before any room
operation. It owns room inventory, branches, URLs, providers, credentials,
background-work rules, deployment mechanics, reseeding, location changes, and
recovery. This reference only defines BuildMo's decision boundary.

Review-room work is external state. Claiming, pushing to a room branch,
reseeding, changing placement/provider, resetting, and releasing each require
explicit authority. Never infer them from Build, QA, or Ship.

## Candidate review

1. Confirm the candidate branch and exact commit.
2. Fetch and rebase it onto current `origin/staging`; resolve and verify on the
   candidate, preserving stack ancestry where applicable.
3. Claim a free room through the supported Main Road interface and record the
   topic, collaborators, candidate PR, location, and database choice supplied
   by the user.
4. Push with the documented force-with-lease procedure.
5. Wait for the room deployment. A frontend response alone is not readiness;
   confirm the required Worker, backend, database, and health evidence.
6. Test through the stable room URLs. For feature-flag journeys, follow the
   current browser user-agent guidance from the room documentation.
7. Record evidence and leave the room claimed while review or a failed reset is
   unresolved.

Reseeding destroys only the room's isolated data but is still destructive; do
it only when explicitly requested. Never expose room credentials.

## Release

After the accepted candidate merges through the normal staging path, reset the
room branch to current `origin/staging` using the documented lease-protected
push. Wait for deployment and backend health before releasing the lease. If
reset or health fails, leave it claimed and report the blocker.

When code adds a cron, recurring timer, startup hook, consumer, or similar
entry point, classify it in the exhaustive review-room trigger inventory and
enforce `BACKGROUND_SCHEDULERS_ENABLED` at the trigger boundary unless the
repository documents it as explicitly request-initiated or a support mechanic.

## Provisioning a new fixed room

Creating a new numbered room is a separate Tier C infrastructure change, not an
extension of claiming or deploying to an existing room. Read and follow the
current provisioning section line by line. First produce a durable plan naming
the repository mappings, branch protection, GitHub Environment, provider apps,
domains, Access policies, database choice, one-time secrets, verification, and
rollback. Stop for explicit authorization before each GitHub, Fly, Cloudflare,
Supabase, DNS, or secret mutation. Never copy credentials from documentation or
another room into chat, logs, state, or committed files.
