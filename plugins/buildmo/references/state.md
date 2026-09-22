# BuildMo state

Keep resumable feature state under `.guru/ux-loop/<slug>.md` in the primary
coordination checkout. `.guru/` is local and ignored. Find the primary checkout
through the repository's worktree information; do not hard-code a teammate's
machine path.

Create the state at the first stage and append history. Update current metadata
when it changes, but never rewrite decision or evidence history.

```markdown
# <Feature>

- slug: <kebab-case>
- started: <YYYY-MM-DD>
- stage: <frame|spec|investigate|build|critique|qa|review-room|ship|done>
- spec: <repo-relative path or none>
- worktree: <absolute local path or none>
- branch: <branch or none>
- base: <branch or none>
- pull request: <URL or none>
- review room: <room id or none>
- serving commit: <commit or none>

## Decisions
- <date> <decision in the user's words>

## Open questions
- <question and owner>

## Evidence
- <date> <source or check and what it established>

## Log
- <date> <stage> — <outcome, changes, verification, deliberate omissions>
```

If the owning domain requires a committed work log, such as a domain-specific
worklog, update that exact file before committing. Do not invent a competing
root `WORKLOG.md` when the repository already declares another record.
