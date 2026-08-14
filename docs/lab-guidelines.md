# Lab Environment Guidelines

This document explains how to set up a safe, isolated environment for every challenge and lab in this repository.

## 1. Virtualization

Use a hypervisor to keep all practice activity contained and reversible:

- **VirtualBox** (free, cross-platform)
- **VMware Workstation Player/Fusion**

Recommended baseline VM specs for an attacker box (Kali Linux):

- 2+ vCPUs
- 4GB+ RAM
- 40GB+ disk

## 2. Recommended Distributions

| Purpose | Distribution |
|---|---|
| Attacker / general purpose | Kali Linux |
| Malware analysis | REMnux, Flare VM (Windows-based) |
| Target practice (web) | Damn Vulnerable Web Application (DVWA), OWASP Juice Shop |
| Target practice (general) | VulnHub images |

## 3. Networking Isolation

**Never** run offensive tools against a network you do not control, including public Wi-Fi, shared office networks, or the open internet.

- Use a **Host-Only** or **Internal Network** adapter in your hypervisor so lab traffic cannot reach the internet or your home network.
- If a challenge requires internet access (e.g., downloading a tool), temporarily switch to NAT, complete the download, then switch back to Host-Only before running any offensive activity.
- Snapshot your VM before starting a challenge so you can revert cleanly.

## 4. Handling Provided Files

Challenge files (binaries, PCAPs, disk images) should be treated as **untrusted**:

- Analyze them inside your isolated VM, never on your host machine.
- Do not execute unknown binaries outside a sandboxed VM, and prefer static analysis first.
- Take a VM snapshot before executing any provided binary.

## 5. Evidence & Artifact Handling

- Store working files (extracted evidence, notes, screenshots) outside version control — see `.gitignore` for patterns already excluded (`*.pcap`, `*.mem`, `evidence/local/`, etc.).
- If you want to share a write-up, sanitize it: remove any real personal data, credentials, or infrastructure details.

## 6. Tool Installation

Most tools referenced in this repository are pre-installed on Kali Linux. Where they are not:

```bash
sudo apt update
sudo apt install <package-name>
```

For Python-based tools:

```bash
python3 -m venv venv
source venv/bin/activate
pip install <package-name>
```

## 7. When You're Done

- Revert your VM snapshot before starting the next unrelated challenge, to avoid state bleeding between exercises.
- Securely delete any real credentials you may have used for testing accounts.

Continue to [`safety-and-ethics.md`](safety-and-ethics.md) for the rules governing what you may and may not target.
