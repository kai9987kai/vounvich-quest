# Security Policy

## Supported Versions

This project is currently a standalone browser game. Security support applies to the latest version on the repository's default branch.

| Version | Supported |
| --- | --- |
| Latest default branch | Yes |
| Older snapshots, forks, and local modifications | No |

## Reporting a Vulnerability

If you find a vulnerability, do not publish exploit details in a public issue.

Use GitHub private vulnerability reporting if it is enabled for the repository. If private reporting is not enabled, open a short public issue asking for a secure maintainer contact and avoid including sensitive technical details.

Please include:

- A summary of the issue.
- Steps to reproduce.
- Affected browser or environment.
- Potential impact.
- Any suggested fix or mitigation.

## Scope

Relevant security issues include:

- Cross-site scripting or unsafe HTML injection in game UI.
- Unsafe handling of local notes, exported state, or `localStorage`.
- Optional browser API behavior that could surprise users, such as camera, speech, WebXR, WebGPU, MIDI, HID, or fullscreen access.
- Supply-chain risk if future dependencies, build tooling, or hosted assets are added.

Out of scope:

- Vulnerabilities in browsers, operating systems, or third-party platforms.
- Social engineering.
- Denial-of-service issues that only affect a user's own local copy.
- Reports based only on unsupported forks or modified builds.

## Disclosure Expectations

Please give maintainers a reasonable opportunity to investigate and fix confirmed issues before public disclosure. Maintainers should acknowledge credible reports within 7 days when possible and provide status updates for accepted reports until the issue is resolved.

## Security Notes for Contributors

- Keep the core game offline-first.
- Avoid adding remote scripts, remote stylesheets, or hidden network calls.
- Use feature detection and explicit user action before invoking sensitive browser APIs.
- Treat imported state, saved notes, and URL-derived data as untrusted.
- Prefer text-safe DOM APIs over raw HTML when rendering user-controlled content.
