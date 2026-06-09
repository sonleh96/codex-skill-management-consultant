# codex-skill-management-consultant

Codex adaptation of the management-consultant skill from
[DogInfantry/claude-skill-management-consultant-B1](https://github.com/DogInfantry/claude-skill-management-consultant-B1).

This repository packages the skill for repeatable installation into Codex across machines.
The installable skill folder is `management-consultant/`.

## What This Skill Does

Use `$management-consultant` in Codex for structured business problem solving, consulting-style case work, market sizing, profitability analysis, market entry, M&A, pricing, operations, digital transformation, org design, due diligence, executive summaries, consulting memos, one-pagers, MECE issue trees, hypothesis-driven analysis, and other strategy consulting tasks.

The skill includes:

- `management-consultant/SKILL.md`: Codex skill entrypoint and workflow.
- `management-consultant/references/`: consulting reference library adapted from the upstream Claude skill.
- `management-consultant/agents/openai.yaml`: Codex UI metadata and default prompt.

## Requirements

- Codex installed and configured on the target machine.
- Git, if installing or updating from this repository.
- A writable Codex skills directory:
  - Windows: `%USERPROFILE%\.codex\skills`
  - macOS/Linux: `~/.codex/skills`

Restart Codex after installing or updating so the skill list is rediscovered.

## Installation

### Windows PowerShell

Clone this repository:

```powershell
git clone https://github.com/<your-org-or-user>/codex-skill-management-consultant.git
```

Create the Codex skills directory if needed:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
```

Install the skill:

```powershell
Copy-Item -Path ".\codex-skill-management-consultant\management-consultant" `
  -Destination "$env:USERPROFILE\.codex\skills\" `
  -Recurse `
  -Force
```

### macOS/Linux

Clone this repository:

```bash
git clone https://github.com/<your-org-or-user>/codex-skill-management-consultant.git
```

Create the Codex skills directory if needed:

```bash
mkdir -p "$HOME/.codex/skills"
```

Install the skill:

```bash
cp -R codex-skill-management-consultant/management-consultant "$HOME/.codex/skills/"
```

## Updating

### Windows PowerShell

From the cloned repository:

```powershell
git pull
Copy-Item -Path ".\management-consultant" `
  -Destination "$env:USERPROFILE\.codex\skills\" `
  -Recurse `
  -Force
```

Restart Codex after the copy completes.

### macOS/Linux

From the cloned repository:

```bash
git pull
rm -rf "$HOME/.codex/skills/management-consultant"
cp -R management-consultant "$HOME/.codex/skills/"
```

Restart Codex after the copy completes.

## Validation

If you have Codex's skill creator utilities available, validate the installed skill with:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" "$env:USERPROFILE\.codex\skills\management-consultant"
```

Expected output:

```text
Skill is valid!
```

## Repository Layout

```text
codex-skill-management-consultant/
├── README.md
├── LICENSE
├── NOTICE
└── management-consultant/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        └── *.md
```

## Attribution

Based on `claude-skill-management-consultant-B1` by DogInfantry:

https://github.com/DogInfantry/claude-skill-management-consultant-B1

This Codex adaptation keeps the upstream consulting reference library and adjusts the skill packaging for Codex discovery, including Codex-compatible trigger metadata and `agents/openai.yaml`.

Upstream source commit used for this package:

```text
0824a1e13bac7cabe7842899c74953c41d26447a
```

## License and Notice

This repository preserves the upstream Apache License, Version 2.0 and NOTICE file.

- See `LICENSE` for the full Apache-2.0 license text.
- See `NOTICE` for upstream attribution and redistribution requirements.

When copying, forking, or redistributing this repository, retain both `LICENSE` and `NOTICE`, and keep visible attribution to DogInfantry and the original repository.

## Disclaimer

This is an independent Codex adaptation. It is not affiliated with or endorsed by OpenAI, Anthropic, Claude, McKinsey, Bain, BCG, or any consulting firm.
