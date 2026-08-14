# Contributing

Thanks for considering a contribution to this repository. Whether you're fixing a typo, adding a link, or contributing a full challenge, this guide explains how to do it consistently.

## Ways to Contribute

- Fix broken links or outdated information.
- Add a new tool, book, course, or platform to `resources/`.
- Add a new challenge or lab.
- Improve existing hints, solutions, or explanations.
- Improve accessibility and clarity of the documentation.

## Adding a New Challenge

1. Copy [`templates/challenge-template.md`](templates/challenge-template.md).
2. Create a new folder under `challenges/` using the naming convention below.
3. Fill in every section — do not leave placeholder text in a submitted PR.
4. Add your challenge to the **Challenge Index** table in the root `README.md`, keeping numbering sequential.
5. Make sure your challenge only targets systems that are legally safe to attack in a lab context (self-hosted vulnerable apps, provided binaries, sample capture files you created or that are freely licensed for training use).

### Naming Conventions

- Challenge folders: `NN-short-kebab-case-title` (e.g., `08-sql-injection-login-bypass`).
- Files inside a challenge folder always use the fixed set: `README.md`, `objectives.md`, `instructions.md`, `hints.md`, `resources.md`, `solution.md`.
- Lab folders: `lab-NN-short-kebab-case-title`.

## Adding a New Lab

1. Copy [`templates/lab-template.md`](templates/lab-template.md).
2. Create a new folder under `labs/`.
3. Add it to the **Labs Index** table in the root `README.md`.

## Markdown Standards

- Use ATX-style headings (`#`, `##`, `###`), not underlines.
- Wrap code, commands, filenames, and flags in backticks.
- Use fenced code blocks with a language hint where possible (` ```bash `, ` ```python `).
- Keep line length reasonable for readability in diffs (no hard requirement, but avoid single-line walls of text).
- Use relative links between files in this repository (e.g., `../../resources/tools.md`), not absolute GitHub URLs.

## Resource Submission Requirements

When adding an entry to any file in `resources/`, include:

```text
Name
Category
Description
Recommended level
Relevant challenges
Official URL
```

- Link only to the **official** source (vendor site, official GitHub repo, official documentation) — not mirrors, forums, or reposts.
- Do not submit paywalled resources without clearly labeling them as paid.
- If you cannot verify a URL is live and correct, label it `[URL REQUIRES VERIFICATION]` rather than omitting or guessing.

## Pull Request Expectations

- One logical change per PR (one new challenge, one resource batch, one doc fix) — keeps review manageable.
- Describe **what** changed and **why** in the PR description.
- Confirm you have tested any commands, scripts, or challenge solutions you are contributing.
- Be prepared to revise based on review feedback — especially around safety framing and technical accuracy.

## Security Considerations

- Never submit real malware samples, real stolen credentials, real exploit code targeting unpatched production software, or links to illegal marketplaces.
- Any binary, script, or capture file you submit must be your own creation or explicitly licensed for redistribution and educational use.
- If you discover a security issue with the repository infrastructure itself (not a challenge topic), follow [`SECURITY.md`](SECURITY.md) instead of opening a public issue.
- All challenge content must assume execution inside an isolated, authorized lab environment — see [`docs/safety-and-ethics.md`](docs/safety-and-ethics.md).

## Code of Conduct

All contributors are expected to follow [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).
