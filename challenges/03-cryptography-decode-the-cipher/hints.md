# Hints

<details>
<summary>Hint 1 (Task A)</summary>

The outer string uses only letters, digits, `+`, `/`, and ends in `==` padding — that's Base64.
</details>

<details>
<summary>Hint 2 (Task A)</summary>

After decoding the Base64, you'll see a string using only `0-9` and `A-F`. That's ASCII text represented as hexadecimal — decode from hex to get readable-ish text.
</details>

<details>
<summary>Hint 3 (Task A)</summary>

The result after hex-decoding still isn't the flag — every letter is shifted by the same fixed amount. Try ROT13 (or CyberChef's "ROT13" / brute-force "ROT13 Brute Force" operation).
</details>

<details>
<summary>Hint 4 (Task B)</summary>

XOR is its own inverse: `ciphertext XOR key = plaintext`, and `plaintext XOR key = ciphertext`. In CyberChef, use "From Hex" followed by "XOR" with your key set to UTF8.
</details>

<details>
<summary>Hint 5 (Task B)</summary>

The key is a common three-letter abbreviation used throughout this entire repository.
</details>
