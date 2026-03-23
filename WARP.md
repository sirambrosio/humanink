# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is

A **Claude Code skill** implemented entirely as Markdown. It detects and rewrites AI-generated text patterns, scores AI probability, and supports multiple writing modes.

## Key files

| File | Purpose |
|------|---------|
| `SKILL.md` | Core skill definition (source of truth). YAML frontmatter + full system prompt with scoring, modes, severity levels, process flow, error handling, multi-language calibration. |
| `PATTERNS.md` | Complete catalog of 35 AI patterns. Detection triggers, before/after examples, cross-language equivalents, severity weights, scoring formula, overlap groups. |
| `STYLEGUIDE.md` | Voice fingerprint framework. How to analyze writing samples and replicate a user's personal style. |
| `README.md` | Installation, usage, feature overview for humans. |
| `WARP.md` | This file. |

### File relationships

```
SKILL.md (brain)
  ├── references PATTERNS.md for pattern details
  └── references STYLEGUIDE.md for voice analysis
README.md (face)
  └── summarizes everything for GitHub visitors
```

When changing behavior: update `SKILL.md` first, then ensure `PATTERNS.md` and `README.md` stay consistent.

## Common commands

### Install
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sirambrosio/humanink.git ~/.claude/skills/humanink
```

### Update
```bash
cd ~/.claude/skills/humanink && git pull
```

### Run in Claude Code
```
/humanink [flags]
```

Available flags: `--academic`, `--casual`, `--corporate`, `--creative`, `--general`, `--light`, `--medium`, `--aggressive`, `--diff`, `--report`, `--score`, `--style`, `--no-audit`, `--explain`, `--pt`, `--es`

## Making changes

### Versioning (keep in sync)
- `SKILL.md` → `version:` in YAML frontmatter
- `README.md` → "Changelog" section
- Bump both when releasing.

### Adding a new pattern
1. Add to `PATTERNS.md` with: number, severity, category, detection triggers, before/after, cross-language equivalents
2. Update scoring weights table in `PATTERNS.md`
3. Add to the summary table in `SKILL.md`
4. Update scoring table in `SKILL.md`
5. Add to the collapsed pattern list in `README.md`
6. Update pattern count in all badges and descriptions (README badges, PATTERNS footer, SKILL description)

### Editing SKILL.md
- Preserve valid YAML frontmatter formatting
- Keep pattern numbering stable (other files reference the same numbers)
- Test flag parsing logic descriptions for clarity

### Documenting fixes
Add a note to README.md's changelog describing what changed and why.

---

## Changelog

| Version | Changes |
|---------|---------|
| **2.2.0** | Context-aware severity matrix (adjusts per mode). Model signatures (ChatGPT/Claude/Gemini pattern clusters). Paragraph-level scoring. Confidence indicator (High/Medium/Low). Rewrite guardrails (DO/DON'T rules). Co-occurrence pairs in SKILL.md. Italian vocabulary and filler phrases. Worked scoring example with step-by-step walkthrough. |
| **2.1.0** | 35 patterns (#33 "Let's dive in", #34 bullet-heavy formatting, #35 unnecessary numbered steps). New flags: `--pt`, `--es` (language shortcuts), `--explain` (inline annotations). Claude.ai skill compatibility. Overlap scoring groups. Threshold gating. Consolidated SKILL.md (scoring + error handling + multi-language inline). |
| **2.0.0** | AI score system, 32 patterns, pattern report, context modes, severity levels, diff output, skip regions, style fingerprint, multi-language calibration. |
| **1.0.0** | Initial release. 24 patterns, two-pass audit. |
