# Cheat Sheets

## Community Cheat Sheets

| Name | Description | Official URL |
|---|---|---|
| Awesome CTF Cheatsheet | General CTF tips and tricks compiled by the community. | [URL REQUIRES VERIFICATION] |
| CTF Wiki Cheatsheet | Tips and tricks maintained by the ISIS Lab CTF wiki. | [URL REQUIRES VERIFICATION] |
| GTFOBins | Curated list of Unix binaries usable to bypass local security restrictions — useful for understanding privilege escalation logic in a lab context. | https://gtfobins.github.io/ |

## Quick Reference — Built Into This Repository

Rather than duplicating maintained external cheat sheets, the following in-repo references summarize the commands most relevant to each category:

### Linux
```bash
ls -la              # list all files including hidden, long format
find / -name "flag*" # search filesystem for files named flag*
grep -r "FLAG{" .    # recursively search text for flag format
chmod +x script.sh   # make a file executable
```

### Forensics
```bash
file suspicious_file       # identify file type by signature, not extension
strings -a suspicious_file # extract printable strings
exiftool image.jpg         # dump metadata
binwalk -e firmware.bin    # extract embedded files
```

### Cryptography
```bash
echo "aGVsbG8=" | base64 -d   # decode base64
echo -n "hello" | xxd -p      # hex encode
```

### Networking
```bash
tshark -r capture.pcap -Y "http"        # filter HTTP traffic
tshark -r capture.pcap --export-objects http,out_dir  # extract transferred files
```

### Reverse Engineering
```bash
file ./binary        # identify architecture/format
strings -a ./binary   # look for hardcoded strings
objdump -d ./binary   # disassemble
```

See each challenge's `resources.md` for category-specific pointers and the relevant tool documentation in [`documentation.md`](documentation.md).
