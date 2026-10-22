# Security policy

## Reporting a vulnerability

Please **do not** open a public issue. Report it privately through GitHub:
**[Security → Report a vulnerability](https://github.com/gr-buildstudio/devmarshal/security/advisories/new)**.

Include what you found, the version (Settings shows it), your operating system, and the steps to reproduce.
We aim to answer within 7 days. A fix is released as soon as it is ready, and you are credited in the
release notes unless you prefer not to be.

## Supported versions

Only the latest release receives security fixes.

## What DevMarshal does to stay safe

- Its server listens only on your own computer (127.0.0.1), behind a one-time launch token and a session
  cookie, with checks against DNS rebinding and cross-site requests.
- AI agents work in a separate Git worktree per mission; your own checkout is not touched, and destructive Git
  operations never run without your explicit approval.
- Secrets in `.env` files are never sent to an agent, and secrets are masked in logs.
- No telemetry. The only outbound request DevMarshal makes itself is the daily "is there a newer version"
  check against this repository, which you can switch off.
