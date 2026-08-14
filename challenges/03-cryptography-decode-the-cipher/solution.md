# Solution Walkthrough

> Attempt the challenge yourself before reading this.

## Task A — Layered Encoding

**Step 1 — Base64 decode:**

```text
NTM1OTRlNTQ3Yjc5NmU2YzcyNjU2NjVmNjI3MzVmNzI2MTcwNjI3MTc2NjE3NDVmNzE3MjcwNjI3MTcyNzE3ZA==
```

decodes to:

```text
53594e547b796e6c7265665f62735f72617062717661745f717270627172717d
```

**Step 2 — Hex decode:**

```text
53594e547b796e6c7265665f62735f72617062717661745f717270627172717d
```

decodes to:

```text
SYNT{ynlref_bs_rapbqvat_qrpbqrq}
```

**Step 3 — ROT13:**

```text
SYNT{ynlref_bs_rapbqvat_qrpbqrq}
```

ROT13'd gives the plaintext flag:

```text
FLAG{layers_of_encoding_decoded}
```

**In CyberChef:** recipe = `From Base64` → `From Hex` → `ROT13`.

## Task B — XOR

**Step 1 — Hex decode:**

```text
253827240f1e0c063952073911471006061552160a0609
```

**Step 2 — XOR with key `ctf` (repeating, byte-by-byte):**

Recovered plaintext:

```text
FLAG{xor_1s_r3vers1ble}
```

**In CyberChef:** recipe = `From Hex` → `XOR` (key: `ctf`, type: UTF8).

## Why This Matters

Real CTF forensics and crypto challenges rarely present a single encoding — you'll routinely encounter Base64-wrapped-hex, or hex-wrapped-Base64-wrapped-XOR. The skill being tested is not "know every cipher" but **pattern recognition of charset and structure**, then applying tools like CyberChef iteratively, one layer at a time. XOR specifically is worth mastering early because it underlies a huge fraction of "encrypted" CTF forensics artifacts and simple malware string obfuscation.
