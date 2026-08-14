# Solution Walkthrough

> Attempt the challenge yourself before reading this.

## Step 1 — Check the File Type

```bash
file vacation_photo.jpg
```

Because the file starts with a valid JPEG header, `file` reports it as `JPEG image data`, even though extra data has been appended after the actual image content — a reminder that `file` only inspects the signature, not the entire file.

## Step 2 — Search for Strings

```bash
strings -a vacation_photo.jpg
```

This reveals the appended plaintext:

```text
FLAG{f1l3_s1gnatur3s_matter}
```

## Step 3 — Check Metadata

```bash
exiftool vacation_photo.jpg
```

Look at the `Comment` field:

```text
Comment: Backup passphrase hint: the first flag is the real one
```

This tells us the flag found via `strings` (appearing *before* the embedded ZIP) is the intended answer, not whatever is inside the embedded archive.

## Step 4 — Detect the Embedded Archive

```bash
binwalk vacation_photo.jpg
```

Output shows two signatures detected: the JPEG header at offset 0, and a ZIP archive signature (`PK\x03\x04`) further into the file.

## Step 5 — Extract It

```bash
binwalk -e vacation_photo.jpg
cat _vacation_photo.jpg.extracted/decoy.txt
```

This reveals:

```text
FLAG{n0t_th3_r3al_0ne}
```

— confirming, per the metadata hint, that this is a decoy planted to test whether you follow every lead uncritically rather than cross-checking evidence.

## Why This Matters

Real forensic investigations regularly contain red herrings. The skill this challenge builds isn't just *finding* hidden data — every tool here (`strings`, `exiftool`, `binwalk`) will readily hand you data — it's **corroborating** findings against each other (in this case, an explicit metadata clue) before reporting a conclusion.
