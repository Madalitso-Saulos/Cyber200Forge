# Hints

<details>
<summary>Hint 1</summary>

`zsteg` has a default mode that tries several common bit-plane/channel-order combinations automatically. Start with just `zsteg filename.png` before trying specific flags like `-a` (try all methods).
</details>

<details>
<summary>Hint 2</summary>

LSB steganography changes only the *last bit* of each color channel value — imperceptible to the eye, but easily read back if you know the same bit order used to embed it.
</details>

<details>
<summary>Hint 3</summary>

`steghide` will simply fail silently or with a generic error if the passphrase is wrong — there's no way to know the correct passphrase from the file alone in this challenge; it's given to you in the scenario text.
</details>

<details>
<summary>Hint 4</summary>

Different embedding tools use different algorithms and storage locations within the file. A tool built to detect one method (e.g., raw LSB) will not necessarily detect data hidden by a different tool (e.g., steghide's own algorithm) — hence needing multiple tools.
</details>
