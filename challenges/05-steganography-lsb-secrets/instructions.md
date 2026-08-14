# Scenario & Instructions

## Scenario

An image titled `team_photo.png` was shared in a "leaked internal chat log" training scenario. Nothing looks unusual to the naked eye, but you suspect a message was hidden using LSB steganography, and possibly a second layer hidden with a passphrase.

## Environment

- **Operating system:** Kali Linux (or any Linux distribution with `zsteg`, `steghide`, and `imagemagick` installed)
- No network access required beyond initial tool installation.

## Setup

Build the scenario file yourself:

```bash
mkdir -p ~/ctf-lab-05 && cd ~/ctf-lab-05

# Create a simple base PNG to work with (requires imagemagick)
convert -size 200x200 xc:skyblue team_photo_base.png

# Hide a message in the LSBs using zsteg-compatible embedding (via a simple Python LSB embed script)
python3 - << 'PYEOF'
from PIL import Image
img = Image.open("team_photo_base.png").convert("RGB")
message = "FLAG{lsb_st3g0_f0und}"
bits = ''.join(format(ord(c), '08b') for c in message) + '00000000'
pixels = list(img.getdata())
new_pixels = []
bit_idx = 0
for pixel in pixels:
    r, g, b = pixel
    if bit_idx < len(bits):
        r = (r & ~1) | int(bits[bit_idx]); bit_idx += 1
    if bit_idx < len(bits):
        g = (g & ~1) | int(bits[bit_idx]); bit_idx += 1
    if bit_idx < len(bits):
        b = (b & ~1) | int(bits[bit_idx]); bit_idx += 1
    new_pixels.append((r, g, b))
img.putdata(new_pixels)
img.save("team_photo.png")
PYEOF

# Hide a second, passphrase-protected message using steghide
echo "FLAG{steghide_p4ssphrase_w0rks}" > second_message.txt
steghide embed -cf team_photo.png -ef second_message.txt -p "trainingctf" -sf team_photo.png
```

> Note: `steghide` only supports JPEG/BMP/WAV/AU cover files reliably in some versions — if it rejects the PNG, convert `team_photo.png` to `team_photo.bmp` first and adjust the commands accordingly.

## Tasks

1. Run `zsteg team_photo.png` (or `team_photo.bmp`) and look for LSB-extractable text.
2. Recover the first hidden flag from the LSB data.
3. Attempt `steghide extract -sf team_photo.png` without a passphrase, and observe the failure.
4. Try the passphrase `trainingctf` and recover the second hidden flag.
5. Explain, in your own words, why two different tools were needed for the two hidden messages.

## Expected Results

Two recovered flags: one purely from LSB analysis, one requiring the correct passphrase.

## Evidence

Save the output of `zsteg` and the successful `steghide extract` command.
