# Scenario & Instructions

## Scenario

You've been given a small Linux command-line utility, `crackme`, that asks for a serial number and only prints a flag if the correct one is provided. There's no obvious way to guess it — you'll need to reverse engineer the binary to recover (or derive) the correct input.

A pre-built sample binary is provided at [`samples/crackme`](samples/crackme). **Do not open the `_SPOILER` source file until after you've solved this challenge or are using `solution.md`.**

## Environment

- **Operating system:** Kali Linux (or any x86-64 Linux distribution)
- **Tools:** `file`, `strings`, Ghidra, GDB

## Setup

```bash
cd challenges/07-reverse-engineering-crackme/samples
chmod +x crackme
./crackme
# Usage: ./crackme <serial>
```

## Tasks

1. Run `file crackme` to confirm architecture and confirm it's not stripped of symbols.
2. Run `strings -a crackme` and note any interesting output (or the lack of an obvious plaintext serial — this binary intentionally obfuscates the check).
3. Load `crackme` into Ghidra, auto-analyze it, and locate the `check_serial` function.
4. Read the decompiled pseudocode. Identify:
   - The expected input length.
   - The obfuscation method used (hint: a single-byte operation applied to each input character before comparison).
   - The byte array it's compared against.
5. Write a short Python script to reverse the obfuscation and recover the correct serial string.
6. Run `./crackme <your_recovered_serial>` and confirm you receive the flag.
7. **Optional (dynamic confirmation):** Set a breakpoint on `check_serial` in GDB, run the binary with a guessed input, and step through to watch the comparison happen live.

## Expected Results

Running `./crackme` with the correct serial should print:

```text
Access granted. Flag: FLAG{...}
```

## Evidence

- A screenshot of the relevant Ghidra decompiled function.
- Your recovery script and its output.
- The final successful `./crackme <serial>` run.
