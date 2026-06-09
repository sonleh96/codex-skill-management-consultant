# codex-skill-management-consultant

Codex adaptation of the management-consultant skill from
[DogInfantry/claude-skill-management-consultant-B1](https://github.com/DogInfantry/claude-skill-management-consultant-B1).

This repository packages the skill for repeatable installation into Codex across machines.
The installable skill folder is `management-consultant/`. Worked case studies and heavy deliverable artifacts live at the repository root for repo-only retrieval.

## What This Skill Does

Use `$management-consultant` in Codex for structured business problem solving, consulting-style case work, market sizing, profitability analysis, market entry, M&A, pricing, operations, digital transformation, org design, due diligence, executive summaries, consulting memos, one-pagers, MECE issue trees, hypothesis-driven analysis, and other strategy consulting tasks.

The skill includes:

- `management-consultant/SKILL.md`: Codex skill entrypoint and workflow.
- `management-consultant/references/`: consulting reference library adapted from the upstream Claude skill.
- `management-consultant/references/index.md`: reference discovery map for progressive loading.
- `management-consultant/references/case-study-index.md`: repo-only case-study retrieval map.
- `management-consultant/agents/openai.yaml`: Codex UI metadata and default prompt.

The repository also includes:

- `CASE-STUDIES.md`: upstream worked-case guide.
- `case-studies/`: upstream case-study artifacts, including Markdown, PDF, XLSX, and HTML deliverables.

Case studies are examples and precedent artifacts. They are not loaded automatically by the skill; use `management-consultant/references/case-study-index.md` to decide which case-study artifact to open.

## Requirements

- Codex installed and configured on the target machine.
- Git, if installing or updating from this repository.
- A writable Codex skills directory.
  - Current Codex documentation commonly uses `~/.agents/skills` for user-level skills.
  - This local Codex desktop install has also discovered skills from `~/.codex/skills`.
  - If both exist, prefer the path used by your active Codex installation.

Restart Codex after installing or updating so the skill list is rediscovered.

## Installation

### Windows PowerShell

Clone this repository and install the skill:

```powershell
git clone https://github.com/sonleh96/codex-skill-management-consultant.git
$skillsDir = "$env:USERPROFILE\.agents\skills"
New-Item -ItemType Directory -Force $skillsDir | Out-Null
Copy-Item -Path ".\codex-skill-management-consultant\management-consultant" `
  -Destination $skillsDir `
  -Recurse `
  -Force
```

If your Codex desktop install uses `.codex\skills`, set `$skillsDir = "$env:USERPROFILE\.codex\skills"` instead.

### macOS/Linux

Clone this repository and install the skill:

```bash
git clone https://github.com/sonleh96/codex-skill-management-consultant.git
skills_dir="$HOME/.agents/skills"
mkdir -p "$skills_dir"
cp -R codex-skill-management-consultant/management-consultant "$skills_dir/"
```

If your Codex install uses `.codex/skills`, set `skills_dir="$HOME/.codex/skills"` instead.

## Updating

### Windows PowerShell

From the cloned repository:

```powershell
git pull
$skillsDir = "$env:USERPROFILE\.agents\skills"
Copy-Item -Path ".\management-consultant" `
  -Destination $skillsDir `
  -Recurse `
  -Force
```

If your Codex desktop install uses `.codex\skills`, set `$skillsDir = "$env:USERPROFILE\.codex\skills"` instead.

Restart Codex after the copy completes.

### macOS/Linux

From the cloned repository:

```bash
git pull
skills_dir="$HOME/.agents/skills"
rm -rf "$skills_dir/management-consultant"
cp -R management-consultant "$skills_dir/"
```

If your Codex install uses `.codex/skills`, set `skills_dir="$HOME/.codex/skills"` instead.

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
├── CASE-STUDIES.md
├── case-studies/
│   └── ...
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
