# Lab 03 — Memory & Disk Forensics

- **Difficulty:** 🔴 Advanced
- **Estimated time:** 2–3 hours

## Objectives

After this lab, you should be able to:

- Mount and browse a disk image without altering evidence.
- Search a mounted filesystem and unallocated space for keywords.
- Explain the high-level workflow for acquiring and analyzing a memory dump.
- Use Autopsy/The Sleuth Kit for structured filesystem analysis.

## Environment

- **Operating system:** Kali Linux VM
- **Tools:** `mount`, The Sleuth Kit / Autopsy, TestDisk or extundelete, (optionally) Volatility for the memory-analysis portion
- **Network configuration:** None required — fully offline lab

## Setup

### Part A — Disk Image

```bash
mkdir -p ~/lab-03/diskimg && cd ~/lab-03/diskimg

# Build a small practice ISO filesystem image containing a hidden flag
mkdir -p iso_root/docs
echo "Quarterly report - nothing interesting here." > iso_root/docs/report.txt
echo "FLAG{mounted_and_found_it}" > iso_root/docs/.hidden_notes
genisoimage -o practice.iso -R iso_root/ 2>/dev/null || mkisofs -o practice.iso -R iso_root/

sudo mkdir -p /mnt/lab03
sudo mount -o loop,ro practice.iso /mnt/lab03
```

### Part B — Autopsy / Sleuth Kit

Point Autopsy (or the `fls`/`icat` command-line tools from The Sleuth Kit) at `practice.iso` as a data source for a structured, evidence-friendly walkthrough of the same content.

## Tasks

1. Use `tree /mnt/lab03` (or `ls -laR`) to review the mounted image's directory structure.
2. Locate the hidden file and read the flag inside it.
3. Unmount the image (`sudo umount /mnt/lab03`) and instead load `practice.iso` into Autopsy as a data source.
4. Within Autopsy, run a keyword search for `FLAG{` across the image and confirm it finds the same file without you needing to browse manually.
5. **Conceptual exercise (no live memory dump required for this lab):** Write a short paragraph describing the four-step memory forensics workflow — acquisition, analysis tool selection, what volatile data you'd expect to find, and why powering down a live system before imaging its memory destroys evidence.

## Expected Results

- The recovered flag from the mounted image.
- A confirmed keyword-search hit for the same flag inside Autopsy.
- A written explanation of the memory forensics workflow.

## Evidence

Screenshot both the manual `tree`/`ls` discovery and the Autopsy keyword search results panel.

## Questions

1. Why is mounting an image **read-only** (`-o loop,ro`) important during a real investigation?
2. What's the practical advantage of a keyword search across an entire image (including unallocated space) versus manually browsing the visible file tree?
3. Why does a memory dump need to be captured *before* a suspect machine is powered off?

## Resources

- [`resources/tools.md`](../../resources/tools.md) — Autopsy, TestDisk, extundelete, Volatility entries
- [`resources/books.md`](../../resources/books.md) — *The Art of Memory Forensics*, *File System Forensic Analysis*
- [`resources/standards-and-frameworks.md`](../../resources/standards-and-frameworks.md) — NIST SP 800-86 *(Recommended Additional Resource)*

## Cleanup

```bash
sudo umount /mnt/lab03 2>/dev/null
rm -rf ~/lab-03
```
