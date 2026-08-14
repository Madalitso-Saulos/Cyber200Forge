# Solution Walkthrough

> Attempt the challenge yourself before reading this.

## Step 1 — Explore

```bash
cd ~/ctf-lab-01
find . -type f
```

This reveals `var/backups/archive.tar.gz`.

## Step 2 — Extract the Archive

```bash
tar -xzf var/backups/archive.tar.gz -C var/backups
```

This extracts the hidden `.hidden/flag.txt` file back into `var/backups/`.

## Step 3 — Fix Permissions

```bash
ls -la var/backups/.hidden/
```

Shows `----------` — no permissions for anyone. Fix it:

```bash
chmod 644 var/backups/.hidden/flag.txt
```

## Step 4 — Read the Flag

```bash
cat var/backups/.hidden/flag.txt
```

Output:

```text
FLAG{linux_f0undat10ns_c0mpl3te}
```

## Step 5 — Confirm With grep

```bash
grep "FLAG{" var/backups/.hidden/flag.txt
```

## Step 6 — Find All .txt Files

```bash
find ~/ctf-lab-01 -type f -name "*.txt"
```

## Why This Matters

Every later category in this repository assumes you can do this without thinking about it: locating files, fixing permission roadblocks, extracting archives, and searching content are the baseline skills used inside forensics, web, and reverse engineering challenges alike.
