# Solution Walkthrough

> Attempt the challenge yourself before reading this.

## Step 1 — Isolate FTP Traffic

In Wireshark's filter bar:

```text
ftp
```

You'll see four packets: `USER`, `331` response, `PASS`, `230` response.

## Step 2 — Follow the TCP Stream

Right-click any of the four FTP packets → **Follow → TCP Stream**. The reconstructed conversation reads:

```text
USER trainee
331 Password required
PASS Sup3rS3cr3t!
230 Login successful
```

**Recovered credentials:** username `trainee`, password `Sup3rS3cr3t!`

## Step 3 — Isolate HTTP Traffic

```text
http
```

You'll see the `GET /notes/flag.txt` request and its `200 OK` response.

## Step 4 — Reconstruct the Transferred File

Right-click the HTTP request or response → **Follow → HTTP Stream**, or use **File → Export Objects → HTTP** and save the object for `/notes/flag.txt`.

The recovered content:

```text
FLAG{pcap_stream_reassembled}
```

## Why This Matters

This challenge demonstrates, hands-on, why protocols like FTP and unencrypted HTTP are considered insecure by design: **anyone positioned to capture the traffic can read everything sent**, including credentials, in plaintext. This is the practical justification behind modern defaults like FTPS/SFTP and HTTPS — it's not an abstract policy, it's directly observable the moment you open a capture in Wireshark.
