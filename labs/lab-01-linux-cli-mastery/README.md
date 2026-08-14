# Lab 01 — Linux CLI Mastery

- **Difficulty:** 🟢 Beginner
- **Estimated time:** 60–90 minutes

## Objectives

After this lab, you should be able to:

- Chain commands using pipes and redirection to solve multi-step problems.
- Use `grep`, `find`, and `awk` together to filter and transform data.
- Manage file permissions and ownership confidently.
- Work comfortably with common archive formats.

## Environment

- **Operating system:** Kali Linux VM (or any Linux distribution)
- **Network configuration:** None required — fully offline lab

## Setup

```bash
mkdir -p ~/lab-01 && cd ~/lab-01
# Generate a small synthetic log dataset to practice on
for i in $(seq 1 50); do
  user=$(shuf -n1 -e alice bob carol dave)
  status=$(shuf -n1 -e 200 200 200 404 500)
  echo "$(date -u +%FT%TZ) user=$user status=$status path=/api/v1/resource/$i" >> access.log
done
chmod 640 access.log
```

## Tasks

1. Count how many log lines belong to each user using `grep`/`awk`.
2. Find every line with a `status=500` and redirect the results into a new file `errors.log`.
3. Use `awk` to print only the `user` and `status` fields for every line.
4. Change `access.log`'s permissions so any user on the system can read it, but only you can write to it.
5. Compress `access.log` and `errors.log` together into `lab-01-evidence.tar.gz`.
6. Use `find` to locate every `.log` file under `~/lab-01`, regardless of how deep it's nested.

## Expected Results

- A correct per-user line count.
- An `errors.log` file containing only 500-status lines.
- A compressed archive containing both log files.

## Evidence

Save your terminal history or a transcript covering each task's command and output.

## Questions

1. What's the difference between `>` and `>>` when redirecting output?
2. Why might you prefer `awk '{print $2, $3}'` over `grep` when you need specific fields rather than whole matching lines?

## Resources

- [`resources/cheat-sheets.md`](../../resources/cheat-sheets.md)
- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) for further practice

## Cleanup

```bash
rm -rf ~/lab-01
```
