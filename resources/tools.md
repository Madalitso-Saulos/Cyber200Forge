# Tools

Tools are grouped by the activity they support. Each entry follows:

```text
Name
Category
Description
Recommended level
Relevant challenges
Official URL
```

---

## Creating Challenges

### Kali Linux CTF Blueprints
- **Category:** Create — general
- **Description:** Online book on building, testing, and customizing your own CTF challenges.
- **Recommended level:** Advanced / instructors
- **Relevant challenges:** N/A (authoring resource)
- **Official URL:** [URL REQUIRES VERIFICATION]

### CTFd
- **Category:** Create — platform
- **Description:** Open-source platform for hosting Jeopardy-style CTFs.
- **Recommended level:** Instructors / event organizers
- **Relevant challenges:** N/A
- **Official URL:** https://ctfd.io/

### PyChallFactory
- **Category:** Create — platform
- **Description:** Small framework to create, manage, and package Jeopardy-style CTF challenges.
- **Recommended level:** Advanced
- **Relevant challenges:** N/A
- **Official URL:** [URL REQUIRES VERIFICATION]

---

## Cryptography

### CyberChef
- **Category:** Crypto / encoding
- **Description:** Browser-based "Cyber Swiss Army Knife" for encoding, decoding, and analyzing data.
- **Recommended level:** Beginner
- **Relevant challenges:** [`03-cryptography-decode-the-cipher`](../challenges/03-cryptography-decode-the-cipher/README.md)
- **Official URL:** https://gchq.github.io/CyberChef/

### QuipQuip
- **Category:** Crypto — classical ciphers
- **Description:** Online tool for breaking substitution or Vigenère ciphers without knowing the key.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`03-cryptography-decode-the-cipher`](../challenges/03-cryptography-decode-the-cipher/README.md)
- **Official URL:** [URL REQUIRES VERIFICATION]

### XORTool
- **Category:** Crypto — XOR analysis
- **Description:** Analyzes multi-byte XOR-encrypted ciphertext to help recover the key.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`03-cryptography-decode-the-cipher`](../challenges/03-cryptography-decode-the-cipher/README.md)
- **Official URL:** https://github.com/hellman/xortool

### RSACTFTool
- **Category:** Crypto — RSA
- **Description:** Attempts multiple known attacks to recover an RSA private key from a weak public key.
- **Recommended level:** Advanced
- **Relevant challenges:** N/A (not yet covered by a starter challenge)
- **Official URL:** https://github.com/Ganapati/RsaCtfTool

### Hash Extender
- **Category:** Crypto — hash length extension
- **Description:** Utility for performing hash length extension attacks.
- **Recommended level:** Advanced
- **Relevant challenges:** N/A
- **Official URL:** [URL REQUIRES VERIFICATION]

---

## Digital Forensics

### exiftool
- **Category:** Forensics — metadata
- **Description:** Reads, writes, and edits metadata across many file formats.
- **Recommended level:** Beginner
- **Relevant challenges:** [`04-digital-forensics-hidden-in-plain-sight`](../challenges/04-digital-forensics-hidden-in-plain-sight/README.md)
- **Official URL:** https://exiftool.org/

### binwalk
- **Category:** Forensics — file carving
- **Description:** Analyzes, reverse engineers, and extracts data/firmware embedded within binary files.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`04-digital-forensics-hidden-in-plain-sight`](../challenges/04-digital-forensics-hidden-in-plain-sight/README.md)
- **Official URL:** https://github.com/ReFirmLabs/binwalk

### Wireshark
- **Category:** Forensics / Networking
- **Description:** The standard GUI tool for capturing and analyzing network traffic (PCAP/PCAPNG).
- **Recommended level:** Beginner–Advanced
- **Relevant challenges:** [`06-network-traffic-analysis`](../challenges/06-network-traffic-analysis/README.md)
- **Official URL:** https://www.wireshark.org/

### Volatility
- **Category:** Forensics — memory analysis
- **Description:** Framework for extracting digital artifacts from volatile memory (RAM) dumps.
- **Recommended level:** Advanced
- **Relevant challenges:** [`labs/lab-03-memory-and-disk-forensics`](../labs/lab-03-memory-and-disk-forensics/README.md)
- **Official URL:** https://www.volatilityfoundation.org/

### Autopsy / The Sleuth Kit
- **Category:** Forensics — filesystem analysis
- **Description:** Open-source digital forensics platform for filesystem and disk image analysis, keyword searches, and unallocated space review.
- **Recommended level:** Intermediate–Advanced
- **Relevant challenges:** [`labs/lab-03-memory-and-disk-forensics`](../labs/lab-03-memory-and-disk-forensics/README.md)
- **Official URL:** https://www.autopsy.com/

### TestDisk / extundelete
- **Category:** Forensics — file recovery
- **Description:** Recover missing partitions and deleted files on FAT/NTFS (TestDisk) and EXT3/EXT4 (extundelete) filesystems.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`labs/lab-03-memory-and-disk-forensics`](../labs/lab-03-memory-and-disk-forensics/README.md)
- **Official URL:** https://www.cgsecurity.org/wiki/TestDisk

---

## Steganography

### Stegsolve
- **Category:** Steganography — image analysis
- **Description:** Applies a range of steganographic techniques (bit planes, color filters) to image files to detect and extract hidden data.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`05-steganography-lsb-secrets`](../challenges/05-steganography-lsb-secrets/README.md)
- **Official URL:** [URL REQUIRES VERIFICATION]

### zsteg
- **Category:** Steganography — PNG/BMP
- **Description:** Detects hidden data in PNG and BMP files, including common LSB patterns.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`05-steganography-lsb-secrets`](../challenges/05-steganography-lsb-secrets/README.md)
- **Official URL:** https://github.com/zed-0xff/zsteg

### Steghide
- **Category:** Steganography — image/audio
- **Description:** Hides and extracts data embedded in image and audio files, optionally with a passphrase.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`05-steganography-lsb-secrets`](../challenges/05-steganography-lsb-secrets/README.md)
- **Official URL:** http://steghide.sourceforge.net/

### StegOnline
- **Category:** Steganography — browser-based
- **Description:** Web-based tool for a wide range of image steganography operations, no local install required.
- **Recommended level:** Beginner
- **Relevant challenges:** [`05-steganography-lsb-secrets`](../challenges/05-steganography-lsb-secrets/README.md)
- **Official URL:** https://georgeom.net/StegOnline/

---

## Reverse Engineering

### Ghidra
- **Category:** Reversing — disassembler/decompiler
- **Description:** Free, open-source software reverse engineering suite from the NSA, including a decompiler.
- **Recommended level:** Intermediate–Advanced
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** https://ghidra-sre.org/

### radare2
- **Category:** Reversing — framework
- **Description:** Portable, scriptable reverse engineering framework with a steep but powerful CLI workflow.
- **Recommended level:** Advanced
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** https://rada.re/n/

### GDB + GEF / Pwndbg
- **Category:** Reversing — dynamic analysis / debugging
- **Description:** The GNU Debugger, enhanced with the GEF or Pwndbg plugin for exploit-development-friendly views.
- **Recommended level:** Intermediate–Advanced
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** https://www.gnu.org/software/gdb/

### Hex Rays (IDA Pro)
- **Category:** Reversing — disassembler/decompiler
- **Description:** Industry-standard commercial disassembler and decompiler.
- **Recommended level:** Advanced
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** https://hex-rays.com/

### OllyDbg
- **Category:** Reversing — dynamic analysis
- **Description:** 32-bit Windows debugger favored for active/dynamic analysis and breakpoint-based stepping.
- **Recommended level:** Intermediate–Advanced
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** http://www.ollydbg.de/

### APKTool / Dex2Jar / Java Decompiler
- **Category:** Reversing — Android
- **Description:** Toolchain for unpacking, converting, and decompiling Android APK files.
- **Recommended level:** Advanced
- **Relevant challenges:** N/A (not covered by a starter challenge)
- **Official URL:** https://ibotpeaches.github.io/Apktool/

### Hex Editor (hexed.it)
- **Category:** Reversing — binary inspection
- **Description:** Browser-based hex editor for inspecting compiled code and raw file bytes when decompilation fails.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`07-reverse-engineering-crackme`](../challenges/07-reverse-engineering-crackme/README.md)
- **Official URL:** https://hexed.it/

---

## Web Exploitation

### Burp Suite
- **Category:** Web — intercepting proxy
- **Description:** The standard tool for intercepting, inspecting, and modifying HTTP requests/responses during web testing.
- **Recommended level:** Beginner–Advanced
- **Relevant challenges:** [`02-web-exploitation-basics`](../challenges/02-web-exploitation-basics/README.md)
- **Official URL:** https://portswigger.net/burp

### OWASP ZAP
- **Category:** Web — intercepting proxy
- **Description:** Free, open-source alternative to Burp Suite for replaying, debugging, and fuzzing HTTP traffic.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`02-web-exploitation-basics`](../challenges/02-web-exploitation-basics/README.md)
- **Official URL:** https://www.zaproxy.org/

### SQLMap
- **Category:** Web — SQL injection
- **Description:** Automated tool for detecting and exploiting SQL injection vulnerabilities.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`02-web-exploitation-basics`](../challenges/02-web-exploitation-basics/README.md)
- **Official URL:** https://sqlmap.org/

### Damn Vulnerable Web Application (DVWA)
- **Category:** Web — vulnerable target
- **Description:** Deliberately vulnerable PHP/MySQL web application for practicing common web attack classes safely.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`02-web-exploitation-basics`](../challenges/02-web-exploitation-basics/README.md), [`labs/lab-02-web-recon-and-intercept`](../labs/lab-02-web-recon-and-intercept/README.md)
- **Official URL:** https://github.com/digininja/DVWA

---

## Networking

### Nmap
- **Category:** Networking — scanning
- **Description:** Open-source utility for network discovery and security auditing.
- **Recommended level:** Beginner–Intermediate
- **Relevant challenges:** [`06-network-traffic-analysis`](../challenges/06-network-traffic-analysis/README.md)
- **Official URL:** https://nmap.org/

### tshark
- **Category:** Networking — CLI packet analysis
- **Description:** Command-line companion to Wireshark for scripted packet capture analysis.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`06-network-traffic-analysis`](../challenges/06-network-traffic-analysis/README.md)
- **Official URL:** https://www.wireshark.org/docs/man-pages/tshark.html

### NetworkMiner
- **Category:** Networking — forensic traffic analysis
- **Description:** Network forensic analysis tool that reconstructs files and sessions from captured traffic.
- **Recommended level:** Intermediate
- **Relevant challenges:** [`06-network-traffic-analysis`](../challenges/06-network-traffic-analysis/README.md)
- **Official URL:** https://www.netresec.com/?page=NetworkMiner

---

## Password / Bruteforce (Reference Only)

> These tools are referenced for completeness from the original source material. They are only appropriate against systems you own or are explicitly authorized to test — see [`docs/safety-and-ethics.md`](../docs/safety-and-ethics.md).

### Hashcat / John the Ripper
- **Category:** Bruteforce — password cracking
- **Description:** Standard offline password-hash cracking tools used to audit password strength in authorized assessments.
- **Recommended level:** Intermediate–Advanced
- **Relevant challenges:** N/A (not covered by a starter challenge)
- **Official URL:** https://hashcat.net/hashcat/ , https://www.openwall.com/john/
