# Security Policy

This repository contains **educational** cybersecurity training material — challenge descriptions, lab guides, and reference documentation. It does not host a live application or service. That said, we take two categories of "security" seriously here.

## 1. Reporting a Problem With Repository Infrastructure or Content

If you find something in this repository that is actually dangerous rather than educational — for example:

- A script or binary that behaves maliciously beyond its stated educational purpose,
- A challenge that inadvertently targets real, non-consenting infrastructure,
- Leaked credentials or genuinely sensitive data accidentally committed,

please **do not** open a public GitHub issue. Instead, report it privately to the maintainers (see repository contact information on the platform hosting this repo) so it can be reviewed and removed or corrected before wider disclosure.

Please include:

- A description of the issue and where it is located (file/path).
- Why you believe it is a problem (not merely a challenge design disagreement).
- Any suggested remediation.

We aim to acknowledge reports within a reasonable timeframe and to correct verified issues promptly.

## 2. Responsible Disclosure for Vulnerabilities Found *While Practicing*

If, while working through a lab or challenge in this repository, you discover a genuine vulnerability in a **third-party tool or platform** referenced here (not something intentionally built into the challenge), please follow that project's own responsible disclosure process rather than reporting it here. Most reputable open-source security tools publish a `SECURITY.md` of their own or a disclosure email address.

## Out of Scope

- Intentional vulnerabilities built into challenges and labs by design (that's the point of a CTF challenge).
- Vulnerabilities in third-party platforms linked from `resources/` — report those to the platform owners directly.

## General Guidance

Never test techniques from this repository against systems you do not own or lack explicit authorization to test. See [`docs/safety-and-ethics.md`](docs/safety-and-ethics.md) for the full policy.
