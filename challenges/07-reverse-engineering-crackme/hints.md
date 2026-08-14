# Hints

<details>
<summary>Hint 1</summary>

Since the binary is not stripped, Ghidra's function list will show meaningfully named functions like `check_serial` directly — you don't need to hunt through `main` first.
</details>

<details>
<summary>Hint 2</summary>

Look for a loop that compares each character of your input against a fixed byte array, one index at a time, after applying some transformation to your input character first.
</details>

<details>
<summary>Hint 3</summary>

The transformation applied is a single XOR against one constant byte value, applied identically to every character. Once you find that constant in the decompiled code, XOR-ing the target array by the same constant recovers the plaintext directly (XOR is its own inverse).
</details>

<details>
<summary>Hint 4</summary>

The expected serial length is checked with `strlen(input) != target_len` early in the function — that tells you exactly how many bytes you're solving for before you even look at the comparison loop.
</details>
