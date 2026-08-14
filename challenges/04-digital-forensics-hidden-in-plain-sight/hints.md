# Hints

<details>
<summary>Hint 1</summary>

`file` only looks at the first few bytes (the file signature) to make its determination — it can be fooled into reporting the wrong type only if those specific leading bytes are altered. Data appended *after* a valid header often won't change what `file` reports.
</details>

<details>
<summary>Hint 2</summary>

`strings -a filename` will surface any plaintext hiding inside otherwise binary data, including text appended after image data.
</details>

<details>
<summary>Hint 3</summary>

Metadata fields like EXIF `Comment` or `UserComment` are easy to overlook but are frequently used to hide notes, hints, or even flags in forensics challenges.
</details>

<details>
<summary>Hint 4</summary>

A ZIP file has its own signature (`PK\x03\x04`) that `binwalk` can detect even when it's appended to the end of another file. Use `binwalk -e` to automatically carve it out.
</details>
