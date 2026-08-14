# Hints

Work through these in order — try each one before revealing the next.

<details>
<summary>Hint 1</summary>

`tar` archives ending in `.tar.gz` are extracted with `tar -xzf filename.tar.gz`. Use `-C` if you want to extract to a specific directory.
</details>

<details>
<summary>Hint 2</summary>

Permissions of `000` mean no one — not even the owner — has read, write, or execute access. You'll need `chmod` to add read permission back, e.g. `chmod 400 file` or `chmod +r file`.
</details>

<details>
<summary>Hint 3</summary>

`find <path> -name "*.txt"` will recursively search for files matching a pattern starting at `<path>`.
</details>

<details>
<summary>Hint 4</summary>

To search file contents for a specific pattern without opening the file, use `grep "FLAG{" filename`.
</details>
