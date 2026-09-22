# Security and external-state floor

Read this when work touches authentication, authorization, user or pupil data,
an endpoint, database, upload, provider, prompt service, analytics, or cloud
configuration.

- Never print or copy a real key, token, password, connection string, `.env`,
  or `.dev.vars` value into code, tests, state, screenshots, logs, or reports.
- Browser-visible environment variables are public. Secrets stay server-side.
- Authenticate a caller and authorize the specific object. Login alone is not
  ownership.
- Validate and bound input at the boundary; reject unknown fields.
- Return only required fields and never expose raw database or stack errors.
- Use the repository's ORM or parameterised queries. Do not pass user input to
  a shell, evaluator, template, redirect, or path without an allowlist.
- Rate-limit unauthenticated, messaging, email, and paid provider actions.
- Validate upload type and size on the server and never trust filenames.
- Prefer no new dependency. Verify the exact package and version when one is
  unavoidable.
- Search the final diff for key-shaped strings and confirm no local credential
  file is tracked.

Changing code does not authorize changing PostHog prompts, feature flags,
provider settings, review rooms, migrations, or deployments. Track local code,
staging deployment, and external configuration as separate states.
