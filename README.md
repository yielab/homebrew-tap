# yielab/homebrew-tap

Homebrew tap for [Tack](https://github.com/yielab/tack), a single-binary project
manager with an agent-execution runner.

```sh
brew install yielab/tap/tack
```

That taps this repository and installs the `tack` binary from the matching
[GitHub Release](https://github.com/yielab/tack/releases). The formula points at
the release archive for your OS and CPU and verifies its SHA-256 digest before
installing; it never builds from source and never downloads anything except that
archive.

Supported: macOS (Apple Silicon and Intel) and Linux x86_64. Linux ARM64 arrives
with the release after `v0.1.0-beta.9`; until then the formula stops with a clear
message rather than installing the wrong binary.

## Formula/tack.rb is generated, not hand-edited

`Formula/tack.rb` is a copy of `packaging/homebrew/tack.rb` from the
[yielab/tack](https://github.com/yielab/tack) repository. It is regenerated there by
`scripts/sync-packaging.sh`, which re-points the version, URLs and digests at a
published release, and pushed here by Tack's release workflow. Changes made here
are overwritten on the next release; send them to the main repository instead.

## How changes land

`main` accepts no direct pushes, from anyone, including the repository's
admins. Every change, human or automated, arrives as a pull request and merges
only when the checks pass:

- `brew audit --strict`, `brew style`, `brew install` and `brew test` on macOS
  and Linux, the same steps Homebrew runs on its own formulae.
- A provenance check: every URL in the formula must be a
  [yielab/tack release asset](https://github.com/yielab/tack/releases), its
  SHA-256 must match the bytes, and the archive must carry a build-provenance
  attestation signed by Tack's release workflow (`gh attestation verify`).

Commits must be signed. Tack's release workflow creates its commit through the
GitHub API, which signs it with GitHub's key, then opens the pull request and
lets it merge once the checks are green. Merges are squash-only and the branch
history is linear, so `git log` on `main` is one signed commit per release.

## Issues, security, license

- Problems with Tack itself go to the
  [main issue tracker](https://github.com/yielab/tack/issues). Open an issue here
  only for a problem with the formula.
- Security reports follow [Tack's security policy](https://github.com/yielab/tack/security/policy);
  see [SECURITY.md](SECURITY.md).
- The formula and this repository are MIT licensed, like Tack ([LICENSE](LICENSE)).
