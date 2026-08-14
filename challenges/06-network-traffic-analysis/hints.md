# Hints

<details>
<summary>Hint 1</summary>

Wireshark's display filter bar accepts protocol names directly — try typing `ftp` or `http` and pressing Enter.
</details>

<details>
<summary>Hint 2</summary>

"Follow TCP Stream" reassembles all packets belonging to one conversation into a single readable view, showing both directions in different colors.
</details>

<details>
<summary>Hint 3</summary>

FTP sends the `USER` and `PASS` commands as separate, unencrypted plaintext lines — look for both in the reconstructed stream.
</details>

<details>
<summary>Hint 4</summary>

`File → Export Objects → HTTP` in Wireshark lists every file-like object Wireshark reassembled from HTTP traffic, and lets you save it directly to disk.
</details>
