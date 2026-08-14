# Resources Overview

This file is a short index into the full resource library in [`resources/`](../resources/). It also documents provenance — what came from the original source material versus what was added.

## Source Material

The core structure, learning progression, and much of the tool/platform content in this repository is derived from:

- An internal CTF onboarding overview covering CTF formats, challenge categories, and beginner platforms.
- An internal beginner's guide to CTF participation covering the hacker mindset, learning progression, Linux/networking foundations, and category deep-dives (web, cryptography, forensics, reverse engineering).
- An internal forensics deep-dive covering file formats, encodings, steganography, filesystem analysis, and network/memory forensics.
- The community-maintained [**Awesome CTF**](https://github.com/apsdehal/awesome-ctf) list (CC0-licensed), covering create/solve tooling and wargame platforms.
- An internal reverse engineering overview covering RE requirements, basic/advanced activities, and practice platforms.

## Recommended Additional Resources

The following were **not** present in the original source material and are added here as clearly-marked supplements, because they are widely recognized, reputable, and directly useful for the stages they support:

- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — industry-standard reference for web application risk categories, useful alongside `challenges/02-web-exploitation-basics`.
- [MITRE ATT&CK](https://attack.mitre.org/) — framework for understanding adversary tactics/techniques, useful context for Stage 7–9 of the learning path.
- [CTFtime](https://ctftime.org/) — the standard community calendar and ranking site for live CTF events, useful for Stage 9 (live participation).
- [NIST SP 800-61 (Computer Security Incident Handling Guide)](https://csrc.nist.gov/pubs/sp/800/61/r2/final) — referenced in `resources/standards-and-frameworks.md` for learners interested in blue-team/incident-response context.

These are marked **[Recommended Additional Resource]** wherever they appear in `resources/`.

## Full Resource Library

| File | Contents |
|---|---|
| [`resources/tools.md`](../resources/tools.md) | Tools grouped by category: create, crypto, bruteforce, exploits, forensics, networking, reversing, steganography, web |
| [`resources/practice-platforms.md`](../resources/practice-platforms.md) | Wargames, beginner platforms, and CTF hosting platforms |
| [`resources/courses.md`](../resources/courses.md) | Structured courses and tutorial series |
| [`resources/books.md`](../resources/books.md) | Recommended reading |
| [`resources/documentation.md`](../resources/documentation.md) | Official documentation links for key tools |
| [`resources/standards-and-frameworks.md`](../resources/standards-and-frameworks.md) | Industry standards and frameworks |
| [`resources/cheat-sheets.md`](../resources/cheat-sheets.md) | Quick-reference sheets |

## URLs Requiring Verification

A small number of URLs referenced in the original source material (primarily niche or regionally hosted wargame platforms) could not be independently re-verified at the time of writing. These are explicitly marked `[URL REQUIRES VERIFICATION]` inline in `resources/practice-platforms.md`. Do not assume they are still live before sharing with learners — check first.
