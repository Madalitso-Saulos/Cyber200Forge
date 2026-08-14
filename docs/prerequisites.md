# Prerequisites

## Baseline Knowledge

No prior cybersecurity experience is required to start Stage 0–1 of the [learning path](learning-path.md). However, the following general skills make progress much faster:

- **Comfort with a computer beyond basic use** — installing software, navigating settings, using a file manager.
- **Basic programming exposure** — even a small amount of Python (variables, loops, conditionals, reading/writing files) is enough to start. You will often be *adapting* existing scripts rather than writing from scratch.
- **Patience with ambiguity** — CTF challenges rarely tell you exactly which tool to use.

## Technical Prerequisites by Stage

| Stage | Required Before Starting |
|---|---|
| Linux Foundations | Ability to install a VM and boot a Linux distribution |
| Web Exploitation | Linux Foundations complete; basic HTML/HTTP familiarity |
| Cryptography | None beyond Stage 0 — good first stop for absolute beginners |
| Digital Forensics | Linux Foundations complete |
| Steganography | Digital Forensics recommended but not required |
| Network Traffic Analysis | Linux Foundations + basic networking concepts |
| Reverse Engineering | Basic C/assembly familiarity recommended; Linux Foundations required |

## Software You Will Need

See [`resources/tools.md`](../resources/tools.md) for the full categorized list. At minimum, install:

1. A hypervisor (VirtualBox or VMware).
2. A Kali Linux (or similar) VM image.
3. A modern web browser with developer tools enabled.

## Hardware Guidance

- 8GB+ RAM recommended if running one attacker VM and one target VM simultaneously.
- 40GB+ free disk space for VM images and downloaded challenge files.
- Virtualization (Intel VT-x / AMD-V) enabled in BIOS/UEFI.

## Skills You Will Build As You Go

You do **not** need to master these before starting — they are built through the challenges themselves:

- Reading Python and modifying existing scripts.
- Parsing JSON/XML output.
- Basic regular expressions.
- Reading disassembled/decompiled C-like pseudocode.

Continue to [`lab-guidelines.md`](lab-guidelines.md) to set up your environment.
