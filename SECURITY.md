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
