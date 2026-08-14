# Cybersecurity Practical Challenges

![License](https://img.shields.io/badge/license-CC0%201.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Contributions](https://img.shields.io/badge/contributions-welcome-orange)
![Level](https://img.shields.io/badge/level-beginner%20to%20advanced-yellow)

A curated, hands-on collection of **Capture The Flag (CTF) style challenges, labs, learning materials, tools, and resources** for anyone who wants to build practical cybersecurity skills — from a first Linux command to reverse engineering a crackme.

This repository was built as a structured learning path rather than a random pile of links. It is organized so a complete beginner can follow it from start to finish, while experienced players can jump straight to the category or difficulty they need.

---

## Table of Contents

- [Purpose](#purpose)
- [Who This Is For](#who-this-is-for)
- [Learning Objectives](#learning-objectives)
- [Topics Covered](#topics-covered)
- [Challenge Categories](#challenge-categories)
- [Difficulty Levels](#difficulty-levels)
- [Prerequisites](#prerequisites)
- [Required Software / Tools](#required-software--tools)
- [Lab Environment Requirements](#lab-environment-requirements)
- [How to Use This Repository](#how-to-use-this-repository)
- [Recommended Learning Path](#recommended-learning-path)
- [Challenge Methodology](#challenge-methodology)
- [Challenge Index](#challenge-index)
- [Labs Index](#labs-index)
- [Resource Library](#resource-library)
- [Repository Structure](#repository-structure)
- [Ethical & Legal Disclaimer](#ethical--legal-disclaimer)
- [Contributing](#contributing)
- [References](#references)

---

## Purpose

Capture The Flag competitions are one of the most effective ways to learn practical cybersecurity: they turn abstract concepts (buffer overflows, SQL injection, packet analysis) into hands-on puzzles with a clear win condition — the flag. This repository exists to:

- Give newcomers a **structured on-ramp** into CTFs instead of a wall of unrelated links.
- Provide **self-contained challenges and labs** with objectives, hints, and solutions.
- Collect a **verified resource library** of tools, platforms, and reading material.
- Model **responsible, ethical practice** — every exercise here is designed for authorized, isolated lab environments only.

## Who This Is For

- Students starting a cybersecurity, computer science, or IT degree.
- Self-taught learners preparing for their first CTF.
- Instructors who want ready-made lab material for a security course.
- Intermediate players who want a refresher path through forensics, crypto, web, and reversing.

## Learning Objectives

By working through this repository, a learner should be able to:

1. Operate confidently on the Linux command line for security tasks.
2. Explain core networking concepts (TCP/UDP, DNS, HTTP) relevant to attack and defense.
3. Identify and exploit common web vulnerabilities (SQLi, XSS, IDOR, directory traversal) in a lab setting.
4. Recognize and decode common encodings and classical ciphers.
5. Perform basic digital forensics: file signature analysis, metadata extraction, steganography detection, and PCAP triage.
6. Perform basic static and dynamic reverse engineering of a simple binary.
7. Apply the "hacker mindset" — questioning trust boundaries and developer assumptions — to new, unseen challenges.

## Topics Covered

| Domain | Description |
|---|---|
| Linux & Command Line | Filesystem navigation, permissions, text processing, networking utilities |
| Networking Fundamentals | TCP/UDP, DNS, HTTP, ports and services |
| Web Exploitation | SQL injection, XSS, CSRF, IDOR, directory traversal, auth bypass |
| Cryptography | Encoding vs. encryption, classical ciphers, XOR, hashing, frequency analysis |
| Digital Forensics | File signatures, metadata, filesystem/disk images, PCAP analysis, memory forensics |
| Steganography | LSB steganography, image/audio hidden-data detection |
| Reverse Engineering | Static/dynamic analysis, disassembly, decompilation, debugging |
| CTF Methodology | Jeopardy vs. Attack-Defense vs. King of the Hill formats |

## Challenge Categories

- 🐧 **Linux Foundations** — command-line proficiency required for everything else.
- 🌐 **Web Exploitation** — finding and exploiting vulnerabilities in web applications.
- 🔐 **Cryptography** — decoding and decrypting ciphertext.
- 🕵️ **Digital Forensics** — recovering hidden or deleted information from files and images.
- 🖼️ **Steganography** — detecting and extracting data hidden inside media files.
- 📡 **Network Traffic Analysis** — inspecting packet captures for exfiltrated data or credentials.
- ⚙️ **Reverse Engineering** — understanding and manipulating compiled binaries.

## Difficulty Levels

| Level | Description |
|---|---|
| 🟢 Beginner | No prior CTF experience assumed; introduces one concept at a time. |
| 🟡 Intermediate | Assumes comfort with Linux and one prior challenge category. |
| 🔴 Advanced | Combines multiple skills; minimal hand-holding. |

## Prerequisites

- Comfort installing and running a virtual machine.
- Basic familiarity with opening a terminal (no prior security experience required for Beginner challenges).
- A willingness to fail, search, and retry — this is the core CTF learning loop.

## Required Software / Tools

- A Linux environment — **Kali Linux** is recommended for its pre-installed tooling.
- A hypervisor: VirtualBox, VMware Workstation/Fusion, or similar.
- [CyberChef](https://gchq.github.io/CyberChef/) for encoding/decoding tasks.
- [Wireshark](https://www.wireshark.org/) for packet analysis.
- [Ghidra](https://ghidra-sre.org/) for reverse engineering.
- A modern browser with developer tools, plus an intercepting proxy such as [Burp Suite](https://portswigger.net/burp).

See [`resources/tools.md`](resources/tools.md) for the full, categorized tool list.

## Lab Environment Requirements

All labs in this repository assume an **isolated virtual lab network**, not production or third-party infrastructure. Recommended baseline:

- Host machine with virtualization support and at least 8GB RAM.
- One attacker VM (Kali Linux or similar).
- One or more target VMs (intentionally vulnerable, e.g., a local instance of Damn Vulnerable Web Application).
- A host-only or NAT network so lab traffic never touches the public internet.

Full setup guidance: [`docs/lab-guidelines.md`](docs/lab-guidelines.md).

## How to Use This Repository

1. Read [`docs/safety-and-ethics.md`](docs/safety-and-ethics.md) first.
2. Review [`docs/prerequisites.md`](docs/prerequisites.md) and set up your lab environment per [`docs/lab-guidelines.md`](docs/lab-guidelines.md).
3. Follow the [Recommended Learning Path](#recommended-learning-path) below, or jump to a specific challenge using the [Challenge Index](#challenge-index).
4. For each challenge: read the `README.md`, attempt the tasks, use `hints.md` only if stuck, and check `solution.md` only after a genuine attempt (or to verify your approach).
5. Use the [Resource Library](#resource-library) to go deeper on any topic.

## Recommended Learning Path

See [`docs/learning-path.md`](docs/learning-path.md) for the full write-up. Summary:

```
01 — Cybersecurity Fundamentals & Hacker Mindset
        ↓
02 — Linux & Networking Foundations
        ↓
03 — Web/Application Security Basics
        ↓
04 — Cryptography Basics
        ↓
05 — Digital Forensics
        ↓
06 — Steganography
        ↓
07 — Network Traffic Analysis
        ↓
08 — Reverse Engineering
        ↓
09 — Live/Practice CTF Participation
```

## Challenge Methodology

Every challenge follows the same loop, adapted from the community-tested CTF learning cycle:

**Play → Fail → Research → Retry → Document**

Each challenge folder contains:

- `README.md` — overview and challenge metadata
- `objectives.md` — what you should be able to do afterward
- `instructions.md` — the scenario and numbered tasks
- `hints.md` — progressive hints (no spoilers up front)
- `resources.md` — links relevant to that specific challenge
- `solution.md` — full walkthrough

## Challenge Index

| # | Challenge | Category | Difficulty | Skills |
|---|---|---|---|---|
| 01 | [Linux Foundations](challenges/01-linux-foundations/README.md) | Linux / Command Line | 🟢 Beginner | Filesystem navigation, permissions, grep/find/awk |
| 02 | [Web Exploitation Basics](challenges/02-web-exploitation-basics/README.md) | Web | 🟢 Beginner | HTTP methods, parameter tampering, IDOR |
| 03 | [Decode the Cipher](challenges/03-cryptography-decode-the-cipher/README.md) | Cryptography | 🟢 Beginner | Base64, ROT/Caesar, XOR, CyberChef |
| 04 | [Hidden in Plain Sight](challenges/04-digital-forensics-hidden-in-plain-sight/README.md) | Forensics | 🟡 Intermediate | File signatures, metadata, `strings`, `exiftool` |
| 05 | [LSB Secrets](challenges/05-steganography-lsb-secrets/README.md) | Steganography | 🟡 Intermediate | LSB stego, `zsteg`, `steghide` |
| 06 | [Network Traffic Analysis](challenges/06-network-traffic-analysis/README.md) | Networking / Forensics | 🟡 Intermediate | Wireshark filters, stream reassembly |
| 07 | [Crackme 101](challenges/07-reverse-engineering-crackme/README.md) | Reverse Engineering | 🔴 Advanced | Static analysis, disassembly, Ghidra |

## Labs Index

| Lab | Focus | Difficulty |
|---|---|---|
| [Lab 01 — Linux CLI Mastery](labs/lab-01-linux-cli-mastery/README.md) | Command-line drills | 🟢 Beginner |
| [Lab 02 — Web Recon & Intercept](labs/lab-02-web-recon-and-intercept/README.md) | Burp Suite / DevTools workflow | 🟡 Intermediate |
| [Lab 03 — Memory & Disk Forensics](labs/lab-03-memory-and-disk-forensics/README.md) | Volatility, disk image mounting | 🔴 Advanced |

## Resource Library

Categorized, verified resources live in [`resources/`](resources/):

- [`tools.md`](resources/tools.md) — tools by category (crypto, forensics, reversing, web, networking, steganography)
- [`practice-platforms.md`](resources/practice-platforms.md) — where to practice (picoCTF, OverTheWire, TryHackMe, Hack The Box, etc.)
- [`courses.md`](resources/courses.md) — structured courses and training paths
- [`books.md`](resources/books.md) — recommended reading
- [`documentation.md`](resources/documentation.md) — official docs for key tools
- [`standards-and-frameworks.md`](resources/standards-and-frameworks.md) — relevant standards
- [`cheat-sheets.md`](resources/cheat-sheets.md) — quick-reference sheets

Additional guidance:

- [`docs/learning-path.md`](docs/learning-path.md)
- [`docs/prerequisites.md`](docs/prerequisites.md)
- [`docs/lab-guidelines.md`](docs/lab-guidelines.md)
- [`docs/safety-and-ethics.md`](docs/safety-and-ethics.md)
- [`docs/resources.md`](docs/resources.md)

## Repository Structure

```text
cybersecurity-practical-challenges/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── CHANGELOG.md
├── .gitignore
├── docs/
│   ├── learning-path.md
│   ├── prerequisites.md
│   ├── lab-guidelines.md
│   ├── safety-and-ethics.md
│   └── resources.md
├── challenges/
│   ├── 01-linux-foundations/
│   ├── 02-web-exploitation-basics/
│   ├── 03-cryptography-decode-the-cipher/
│   ├── 04-digital-forensics-hidden-in-plain-sight/
│   ├── 05-steganography-lsb-secrets/
│   ├── 06-network-traffic-analysis/
│   └── 07-reverse-engineering-crackme/
├── labs/
│   ├── lab-01-linux-cli-mastery/
│   ├── lab-02-web-recon-and-intercept/
│   └── lab-03-memory-and-disk-forensics/
├── resources/
│   ├── tools.md
│   ├── books.md
│   ├── courses.md
│   ├── documentation.md
│   ├── standards-and-frameworks.md
│   ├── practice-platforms.md
│   └── cheat-sheets.md
├── templates/
│   ├── challenge-template.md
│   ├── lab-template.md
│   └── lab-report-template.md
├── scripts/
│   └── README.md
└── assets/
    └── images/
```

## Ethical & Legal Disclaimer

All material in this repository is provided **for educational purposes only**, to be practiced exclusively against:

- Your own personal lab systems,
- Systems you are explicitly authorized to test,
- Intentionally vulnerable applications and VMs built for training (e.g., DVWA, VulnHub images),
- Recognized CTF and wargame platforms (e.g., picoCTF, OverTheWire, Hack The Box, TryHackMe).

**Do not** use any technique, tool, or script in this repository against systems you do not own or do not have explicit written authorization to test. Unauthorized access to computer systems is illegal in most jurisdictions. See [`docs/safety-and-ethics.md`](docs/safety-and-ethics.md) for full guidance.

## Contributing

Contributions are welcome — new challenges, corrected links, and additional resources all help. Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening a pull request.

## References

Primary source material for this repository's learning path, forensics, and reverse-engineering content was drawn from an internal CTF onboarding guide and a beginner's guide to CTF participation, along with the community-maintained [Awesome CTF](https://github.com/apsdehal/awesome-ctf) list. Where content was added beyond the original source material, it is marked in [`docs/resources.md`](docs/resources.md) as a **Recommended Additional Resource**.
