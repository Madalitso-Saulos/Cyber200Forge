# Recommended Learning Path

CTF performance follows a hierarchy, not a tool list:

```
Mindset → Conceptual Knowledge → Operating System Skills → Programming Logic → Security Techniques → Tools
```

Most beginners try to skip straight to "tools" and stall out. This path builds the layers underneath first.

## Stage 0 — Hacker Mindset

Before any technical content, internalize the attacker's questions:

- What did the developer assume?
- What input is trusted that shouldn't be?
- What was forgotten (an edge case, an old endpoint, a debug flag)?
- What leaks information (error messages, headers, metadata, timing)?

**Completion criteria:** you can look at an unfamiliar login form or file and immediately list 3+ things you'd want to test.

## Stage 1 — Linux & Networking Foundations

- **Knowledge requirements:** filesystem navigation, permissions, pipes/redirection, `grep`/`find`/`awk`, archive formats, and core networking utilities (`netstat`, `nc`, `curl`, `ssh`).
- **Recommended challenge:** [`challenges/01-linux-foundations`](../challenges/01-linux-foundations/README.md)
- **Recommended lab:** [`labs/lab-01-linux-cli-mastery`](../labs/lab-01-linux-cli-mastery/README.md)
- **Tools:** bash, OverTheWire Bandit
- **Expected skills:** comfortable working entirely from a terminal; can explain TCP vs. UDP and basic DNS lookups.
- **Completion criteria:** finish the Linux Foundations challenge and at least the first 10 levels of OverTheWire Bandit.

## Stage 2 — Security Fundamentals & CTF Formats

- **Knowledge requirements:** understand Jeopardy-style, Attack-Defense, and King of the Hill CTF formats; understand flag formats and scoring.
- **Resources:** [`docs/resources.md`](resources.md), root `README.md` challenge methodology section.
- **Completion criteria:** can describe, in your own words, the difference between the three CTF formats and pick the right practice platform for your current skill level.

## Stage 3 — Web / Application Security

- **Knowledge requirements:** HTTP methods, cookies/sessions, parameter manipulation, SQL injection, XSS, CSRF, IDOR, directory traversal, file inclusion, authentication bypass.
- **Recommended challenge:** [`challenges/02-web-exploitation-basics`](../challenges/02-web-exploitation-basics/README.md)
- **Recommended lab:** [`labs/lab-02-web-recon-and-intercept`](../labs/lab-02-web-recon-and-intercept/README.md)
- **Tools:** Burp Suite, browser DevTools, Damn Vulnerable Web Application (DVWA)
- **Completion criteria:** successfully intercept and modify a request to bypass a client-side check in a lab app.

## Stage 4 — Cryptography

- **Knowledge requirements:** Base64, hex, binary, ROT/Caesar ciphers, URL encoding, XOR, frequency analysis, hashing.
- **Recommended challenge:** [`challenges/03-cryptography-decode-the-cipher`](../challenges/03-cryptography-decode-the-cipher/README.md)
- **Tools:** CyberChef
- **Completion criteria:** given an unlabeled ciphertext, correctly identify the encoding/cipher family and recover the plaintext.

## Stage 5 — Digital Forensics

- **Knowledge requirements:** file signatures, metadata extraction, archive inspection, filesystem structures (FAT/NTFS/EXT), deleted-file recovery concepts.
- **Recommended challenge:** [`challenges/04-digital-forensics-hidden-in-plain-sight`](../challenges/04-digital-forensics-hidden-in-plain-sight/README.md)
- **Tools:** `file`, `strings`, `binwalk`, `exiftool`, Autopsy
- **Completion criteria:** recover a flag hidden via a mismatched file signature and confirm it using metadata analysis.

## Stage 6 — Steganography

- **Knowledge requirements:** LSB steganography concepts, common stego tool signatures.
- **Recommended challenge:** [`challenges/05-steganography-lsb-secrets`](../challenges/05-steganography-lsb-secrets/README.md)
- **Tools:** Stegsolve, zsteg, Steghide, StegOnline
- **Completion criteria:** extract a hidden message from an image using at least two different techniques.

## Stage 7 — Network Traffic Analysis

- **Knowledge requirements:** PCAP structure, Wireshark filters, stream reassembly, common protocols (HTTP, FTP, DNS).
- **Recommended challenge:** [`challenges/06-network-traffic-analysis`](../challenges/06-network-traffic-analysis/README.md)
- **Recommended lab:** [`labs/lab-03-memory-and-disk-forensics`](../labs/lab-03-memory-and-disk-forensics/README.md) (combined with memory forensics)
- **Tools:** Wireshark, `tshark`, NetworkMiner
- **Completion criteria:** reconstruct a file transferred in a provided PCAP.

## Stage 8 — Reverse Engineering

- **Knowledge requirements:** file type identification, static analysis (`strings`, disassembly), dynamic analysis (debugging), recognizing loops/conditionals/function calls in decompiled output.
- **Recommended challenge:** [`challenges/07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Tools:** Ghidra, GDB/GEF/Pwndbg, radare2
- **Completion criteria:** recover a hardcoded validation key from a simple crackme binary without access to source code.

## Stage 9 — Live / Practice CTF Participation

- **Action:** join a beginner-friendly live CTF (check [CTFtime](https://ctftime.org/)) or work continuously through picoGym, OverTheWire, or TryHackMe rooms.
- **Completion criteria:** capture your first flag in a live, timed competition — then write it up. See [`templates/lab-report-template.md`](../templates/lab-report-template.md).

## The One Rule

If you remember nothing else:

> **Play → Fail → Research → Retry → Document.** Repeat hundreds of times.

Reliance on write-ups should be limited — new skills are best learned by solving the problem yourself first.
