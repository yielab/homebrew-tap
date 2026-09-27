# Security Policy

This repository holds only a Homebrew formula. It ships no code of its own: the
formula downloads a release archive published by
[yielab/tack](https://github.com/yielab/tack) and checks its SHA-256 digest
before installing.

**Please do not open a public issue for security vulnerabilities.**

- A vulnerability in Tack itself follows
  [Tack's security policy](https://github.com/yielab/tack/security/policy).
- A problem with the formula (a wrong digest, a URL pointing somewhere it should
  not, a tampered file in this repository) should be reported privately through
  [GitHub Security Advisories on yielab/tack](https://github.com/yielab/tack/security/advisories/new),
  or by email to **[info@yielab.com](mailto:info@yielab.com)** with the subject
  `[tack] security`.

Acknowledgement within 7 days; a fix is released before public details.

## What protects this repository

- `main` takes no direct pushes; every change is a pull request that must pass
  the checks in `.github/workflows/test.yml`, which verify that each archive
  the formula points at is a yielab/tack release asset with a matching digest
  and a build-provenance attestation signed by Tack's release workflow.
- Commits on `main` must carry a verified signature. The release automation
  commits through the GitHub API, so its commits are signed by GitHub.
- No account, including admins, can bypass those rules; changing them is a
  visible change to the repository's rulesets.
- The workflow token is read-only. The credential Tack's release workflow uses
  to open pull requests here is a fine-grained token scoped to this one
  repository, with contents and pull-request write access and nothing else.
- Secret scanning with push protection and Dependabot are enabled.
