# Scenario & Instructions

## Scenario

You've just been handed access to a training VM. Somewhere on the filesystem, a previous user left a flag file behind — but they also left permission errors, a locked archive, and a maze of nested directories in your way. Your job is to use nothing but the command line to track it down.

## Environment

- **Operating system:** Kali Linux (or any modern Linux distribution)
- **Tools required:** bash, `find`, `grep`, `awk`, `chmod`, `tar`/`unzip`
- No network access is required for this challenge.

## Setup

This challenge is designed to be self-built as practice — create the scenario yourself to reinforce the commands, then solve it:

```bash
mkdir -p ~/ctf-lab-01/var/backups/.hidden
cd ~/ctf-lab-01
echo "FLAG{linux_f0undat10ns_c0mpl3te}" > var/backups/.hidden/flag.txt
chmod 000 var/backups/.hidden/flag.txt
tar -czf var/backups/archive.tar.gz -C var/backups .hidden
rm -rf var/backups/.hidden
```

This recreates a realistic scenario: a flag file compressed inside an archive, originally created with permissions that would have blocked reading it.

## Tasks

1. Explore `~/ctf-lab-01` and identify what's inside `var/backups/`.
2. Extract `archive.tar.gz` to reveal its contents.
3. Notice the extracted flag file has restrictive permissions — fix them so you can read it.
4. Read the flag using `cat`.
5. Use `grep` to confirm the flag matches the format `FLAG{...}` without opening the file in an editor.
6. Use `find` to locate every `.txt` file under `~/ctf-lab-01` in one command.

## Expected Results

You should be able to print the flag string to your terminal using only command-line tools, and explain each step you took.

## Evidence

Capture a terminal transcript (or screenshot) showing:
- The `tar` extraction command and output.
- The `chmod` command you used to fix permissions.
- The final `cat` or `grep` command that reveals the flag.
