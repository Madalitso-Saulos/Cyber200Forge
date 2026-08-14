# Solution Walkthrough

> Attempt the challenge yourself before reading this. The full annotated source is also available at `samples/crackme_source_SPOILER.c.txt` for after you've solved it.

## Step 1 — Identify the Binary

```bash
file crackme
```

```text
crackme: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, ... not stripped
```

Not stripped means function names like `check_serial` survive in the symbol table — a big head start.

## Step 2 — Strings

```bash
strings -a crackme
```

You'll see `Usage:`, `Access granted. Flag: FLAG{...}` is present as a *format string* fragment, but the actual serial required is **not** present in plaintext — it's stored as an obfuscated byte array, so `strings` alone won't hand you the answer.

## Step 3 — Disassemble/Decompile in Ghidra

Open `crackme` in Ghidra, let auto-analysis run, then open `check_serial` in the Decompiler view. You'll see logic equivalent to:

```c
if (strlen(input) != 29) return 0;
for (i = 0; i < 29; i++) {
    if ((input[i] ^ 0x2A) != target[i]) return 0;
}
return 1;
```

Two key facts to extract:
- **Expected length:** 29 characters.
- **Obfuscation:** each input byte is XORed with `0x2A` before comparison against the `target` array.

You can read the `target` array's byte values directly from Ghidra's data view (or from the disassembly's immediate values in the comparison instructions).

## Step 4 — Recover the Serial

Since XOR is its own inverse, XOR-ing every byte of `target` with `0x2A` gives the correct plaintext serial directly:

```python
target = [0x1c,0x0e,0x02,0x0e,0x1d,0x02,0x51,0x02,0x18,0x1d,0x51,0x02,
          0x0c,0x1d,0x51,0x1e,0x1a,0x50,0x1c,0x02,0x1d,0x00,0x0d,0x1c,
          0x00,0x1d,0x1e,0x53,0x00]
key = 0x2A
serial = ''.join(chr(b ^ key) for b in target)
print(serial)
```

## Step 5 — Confirm

```bash
./crackme "<recovered_serial>"
```

Output:

```text
Access granted. Flag: FLAG{crackme_101_solved}
```

## Step 6 — (Optional) Dynamic Confirmation With GDB

```bash
gdb ./crackme
(gdb) break check_serial
(gdb) run "wrong_guess_of_correct_length_______"
(gdb) info registers
(gdb) x/29xb $rdi   # inspect the input buffer byte-by-byte
```

Stepping through the comparison loop with `stepi`/`next` lets you watch each XOR-and-compare happen live, confirming the static analysis was correct.

## Why This Matters

This challenge illustrates the standard reverse-engineering loop: **check the file type → look for low-hanging fruit with `strings` → move to static disassembly/decompilation when strings alone aren't enough → confirm your hypothesis dynamically.** The specific obfuscation here (single-byte XOR) is deliberately simple — real-world crackmes and malware use nested, multi-stage, or key-derived obfuscation, but the workflow scales directly from this exercise.
