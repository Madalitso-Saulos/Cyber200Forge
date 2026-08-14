# Scenario & Instructions

## Scenario

During an authorized lab exercise, your team captured a short segment of network traffic from a training network. Somewhere in that capture, a file was transferred in the clear over HTTP, and a user's plaintext login credentials were sent over FTP. Your job is to reconstruct both.

## Environment

- **Operating system:** Kali Linux (or any distribution with Wireshark/tshark)
- **Tools:** Wireshark, `tshark`, optionally `python3` with `scapy` to build the sample capture yourself

## Setup

Generate a sample capture to practice on, using Python's `scapy` (install with `pip install scapy --break-system-packages` if needed) inside your isolated lab VM:

```python
# generate_pcap.py — run inside your isolated lab environment only
from scapy.all import *

packets = []

# Simulated FTP login in cleartext
packets += [
    Ether()/IP(src="10.0.0.5", dst="10.0.0.10")/TCP(sport=51410, dport=21)/Raw(load=b"USER trainee\r\n"),
    Ether()/IP(src="10.0.0.10", dst="10.0.0.5")/TCP(sport=21, dport=51410)/Raw(load=b"331 Password required\r\n"),
    Ether()/IP(src="10.0.0.5", dst="10.0.0.10")/TCP(sport=51410, dport=21)/Raw(load=b"PASS Sup3rS3cr3t!\r\n"),
    Ether()/IP(src="10.0.0.10", dst="10.0.0.5")/TCP(sport=21, dport=51410)/Raw(load=b"230 Login successful\r\n"),
]

# Simulated HTTP GET transferring a small text "file"
http_request = b"GET /notes/flag.txt HTTP/1.1\r\nHost: intranet.lab\r\n\r\n"
http_response = (
    b"HTTP/1.1 200 OK\r\nContent-Type: text/plain\r\n"
    b"Content-Length: 30\r\n\r\nFLAG{pcap_stream_reassembled}"
)
packets += [
    Ether()/IP(src="10.0.0.5", dst="10.0.0.20")/TCP(sport=51420, dport=80)/Raw(load=http_request),
    Ether()/IP(src="10.0.0.20", dst="10.0.0.5")/TCP(sport=80, dport=51420)/Raw(load=http_response),
]

wrpcap("training_capture.pcap", packets)
print("Wrote training_capture.pcap")
```

Run it: `python3 generate_pcap.py`

## Tasks

1. Open `training_capture.pcap` in Wireshark.
2. Apply a display filter to isolate FTP traffic only.
3. Right-click an FTP packet and select "Follow → TCP Stream" to reconstruct the login sequence.
4. Record the username and password sent in cleartext.
5. Apply a display filter to isolate HTTP traffic only.
6. Use "Follow → HTTP Stream" (or `File → Export Objects → HTTP`) to recover the transferred file content.
7. Record the flag contained in the transferred file.

## Expected Results

- Recovered FTP username and password.
- Recovered flag from the HTTP-transferred file.

## Evidence

Screenshot the "Follow TCP Stream" windows for both the FTP and HTTP conversations.
