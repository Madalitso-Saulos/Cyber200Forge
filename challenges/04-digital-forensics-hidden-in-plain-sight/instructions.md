# Scenario & Instructions

## Scenario

A colleague found a file named `vacation_photo.jpg` in a suspicious email attachment during an authorized incident-response exercise. Something about it feels off — it's larger than a normal photo and won't open properly in some viewers. Your job is to determine what it actually is and recover any hidden data.

## Environment

- **Operating system:** Kali Linux (or any Linux distribution with `file`, `strings`, `binwalk`, `exiftool` installed)
- No network access required.

## Setup

Build the scenario file yourself to practice the full workflow:

```bash
mkdir -p ~/ctf-lab-04 && cd ~/ctf-lab-04

# Start with a minimal valid JPEG header so `file` initially reports it as a JPEG
printf '\xff\xd8\xff\xe0\x00\x10JFIF\x00\x01\x01\x00\x00\x01\x00\x01\x00\x00' > vacation_photo.jpg

# Append a hidden text flag
echo "FLAG{f1l3_s1gnatur3s_matter}" >> vacation_photo.jpg

# Append a small embedded ZIP archive containing a second, decoy flag
echo "FLAG{n0t_th3_r3al_0ne}" > decoy.txt
zip -q hidden.zip decoy.txt
cat hidden.zip >> vacation_photo.jpg

# Add EXIF-style metadata comment (requires exiftool)
exiftool -Comment="Backup passphrase hint: the first flag is the real one" -overwrite_original vacation_photo.jpg 2>/dev/null || true
```

## Tasks

1. Run `file vacation_photo.jpg` and confirm whether it is reported as a valid JPEG.
2. Run `strings -a vacation_photo.jpg` and look for any readable flag-like strings.
3. Run `exiftool vacation_photo.jpg` and check for anything unusual in the metadata.
4. Run `binwalk vacation_photo.jpg` to check for embedded file signatures beyond the JPEG data.
5. If `binwalk` reports an embedded archive, extract it with `binwalk -e vacation_photo.jpg` and inspect the result.
6. Determine which of the two flags found is the "real" one, based on the metadata hint, and explain why the other is a decoy.

## Expected Results

You should recover **two** flag-like strings from the file, but be able to explain — using the metadata clue — which one is the intended answer.

## Evidence

Save the output of each command (`file`, `strings`, `exiftool`, `binwalk`) as your evidence trail.
