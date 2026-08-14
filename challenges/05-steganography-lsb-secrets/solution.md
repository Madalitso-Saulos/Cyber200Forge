# Solution Walkthrough

> Attempt the challenge yourself before reading this.

## Step 1 — Run zsteg

```bash
zsteg team_photo.png
```

Among the output lines, one of the LSB channel combinations (commonly `b1,rgb,lsb,xy` or similar, depending on embed order) will show readable text:

```text
FLAG{lsb_st3g0_f0und}
```

If the default scan doesn't surface it immediately, try:

```bash
zsteg -a team_photo.png
```

to run zsteg's exhaustive method list.

## Step 2 — Attempt steghide Without a Passphrase

```bash
steghide extract -sf team_photo.png
```

This fails or prompts for a passphrase — steghide's embedded data is encrypted and cannot be extracted without it.

## Step 3 — Extract With the Given Passphrase

```bash
steghide extract -sf team_photo.png -p "trainingctf"
```

This produces `second_message.txt`, containing:

```text
FLAG{steghide_p4ssphrase_w0rks}
```

## Why This Matters

This challenge deliberately layers two different steganographic techniques to illustrate a core forensics/stego lesson: **there is no single tool that detects everything.** LSB steganography embedded "by hand" (or by a custom script) is visible to bit-plane analysis tools like `zsteg`, but a dedicated tool like `steghide` uses its own embedding algorithm and encryption, invisible to `zsteg`'s heuristics and requiring the correct passphrase to recover. Real steganography challenges often require this same "try several tools" persistence.
