# Safety & Ethics

This repository teaches offensive security *techniques* for defensive and educational purposes. That comes with a responsibility to be explicit about scope.

## What You May Target

You may only apply the techniques in this repository against:

- **Personal lab systems** you own and control.
- **Systems you have explicit, documented authorization to test** (e.g., an employer's pre-approved penetration test with signed scope).
- **Intentionally vulnerable applications and VMs** built for training (DVWA, OWASP Juice Shop, VulnHub images, etc.).
- **Recognized CTF and wargame platforms** during an active event or open practice mode (picoCTF/picoGym, OverTheWire, Hack The Box, TryHackMe, Root-Me, and similar).
- **Systems for which explicit written permission has been granted** by the owner.

## What You May Never Do

- Do not scan, probe, or attack systems you do not own or lack authorization to test — including "just looking" reconnaissance against real infrastructure.
- Do not use techniques learned here to access accounts, data, or systems belonging to others without consent.
- Do not deploy anything from this repository against production systems, even ones you administer, without a formal change/testing window.
- Do not use these skills to bypass paywalls, DRM, or licensing on software or media you have not purchased or are not licensed to modify.

## Why This Matters

Unauthorized access to computer systems is a criminal offense in most jurisdictions (for example, under laws such as the U.S. Computer Fraud and Abuse Act, the UK Computer Misuse Act, and equivalent legislation elsewhere), regardless of intent or whether damage occurred. "I was just testing" is not a legal defense for accessing a system without authorization.

## Responsible Practice Habits

- Keep a written record of what you had authorization to test and from whom, for any non-lab engagement.
- When practicing on public wargame/CTF platforms, follow that platform's specific rules of engagement (some platforms disallow brute-forcing their own login pages, DoS attacks, or scanning outside the designated target range).
- If you discover a real vulnerability in software or a service *outside* of an authorized test, follow responsible/coordinated disclosure — report it to the vendor rather than exploiting or publicizing it. See [`SECURITY.md`](../SECURITY.md) for this repository's own disclosure process.

## Reporting Concerns About This Repository

If you believe any challenge, script, or piece of guidance in this repository crosses from "educational, lab-scoped" into something that could cause real-world harm, please report it per [`SECURITY.md`](../SECURITY.md) rather than opening a public issue.
