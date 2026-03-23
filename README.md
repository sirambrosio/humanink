<p align="center">
  <br/>
  <br/>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=42&duration=3000&pause=1000&color=FFFFFF&center=true&vCenter=true&repeat=false&width=435&lines=HumanInk">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=42&duration=3000&pause=1000&color=000000&center=true&vCenter=true&repeat=false&width=435&lines=HumanInk" alt="HumanInk — AI Writing Detector and Humanizer" />
  </picture>
  <br/>
  <br/>
</p>

# HumanInk — AI Writing Detector & Humanizer for Claude

> **Strip the AI. Keep the meaning. Sound human again.**
>
> Detects 35 AI writing patterns, scores AI probability 0-100, identifies ChatGPT / Claude / Gemini signatures, and rewrites text in your personal voice. No code. No dependencies. Pure Markdown skill for Claude Code & Claude.ai.

<p align="center">
  <a href="#quick-start--installation"><img src="https://img.shields.io/badge/GET_STARTED-000000?style=for-the-badge" alt="get started" /></a>
  &nbsp;
  <a href="#35-ai-writing-patterns-detected"><img src="https://img.shields.io/badge/35_PATTERNS-E34234?style=for-the-badge" alt="patterns" /></a>
  &nbsp;
  <a href="#ai-probability-score-system"><img src="https://img.shields.io/badge/AI_SCORE-5A45FF?style=for-the-badge" alt="score" /></a>
  &nbsp;
  <a href="#before--after--real-example"><img src="https://img.shields.io/badge/EXAMPLE-22c55e?style=for-the-badge" alt="example" /></a>
  <br/>
  <br/>
  <img src="https://img.shields.io/badge/v2.2.0-111?style=flat-square&logo=semver&logoColor=white" alt="version" />
  &nbsp;
  <a href="https://github.com/sirambrosio/humanink/stargazers"><img src="https://img.shields.io/github/stars/sirambrosio/humanink?style=flat-square&logo=github&logoColor=white&label=stars" alt="GitHub stars" /></a>
  &nbsp;
  <a href="https://github.com/sirambrosio/humanink/network/members"><img src="https://img.shields.io/github/forks/sirambrosio/humanink?style=flat-square&logo=github&logoColor=white&label=forks" alt="GitHub forks" /></a>
  &nbsp;
  <a href="https://github.com/sirambrosio/humanink/commits/main"><img src="https://img.shields.io/github/last-commit/sirambrosio/humanink?style=flat-square&logo=github&logoColor=white&label=last%20commit" alt="Last commit" /></a>
  &nbsp;
  <img src="https://img.shields.io/badge/Claude_Code_+_Claude.ai-5A45FF?style=flat-square&logo=anthropic&logoColor=white" alt="platform" />
  &nbsp;
  <img src="https://img.shields.io/badge/35_patterns-E34234?style=flat-square" alt="patterns" />
  &nbsp;
  <img src="https://img.shields.io/badge/7_languages-0969da?style=flat-square&logo=google-translate&logoColor=white" alt="languages" />
  &nbsp;
  <a href="LICENSE"><img src="https://img.shields.io/badge/MIT-22c55e?style=flat-square&logo=opensourceinitiative&logoColor=white" alt="license" /></a>
  <br/>
  <br/>
  <sub>If this helps you write better, consider giving it a <a href="https://github.com/sirambrosio/humanink">star</a> — it helps others find it.</sub>
  <br/>
  <br/>
</p>

---

## Table of Contents

- [Why HumanInk exists](#why-humanink-exists)
- [Features](#features--what-humanink-does)
- [How HumanInk detects AI writing patterns](#how-humanink-detects-ai-writing-patterns)
- [Quick start / Installation](#quick-start--installation)
- [AI probability score system](#ai-probability-score-system)
- [Context modes and flags](#context-modes-and-flags)
- [Before / After — Real example](#before--after--real-example)
- [35 AI writing patterns detected](#35-ai-writing-patterns-detected)
- [Style fingerprint — Write in your voice](#style-fingerprint--write-in-your-voice)
- [Multi-language AI detection](#multi-language-ai-detection)
- [Model signature detection](#model-signature-detection--chatgpt-vs-claude-vs-gemini)
- [Project structure](#project-structure)
- [FAQ](#faq)
- [Contributing](#contributing)
- [References](#references)
- [Changelog](#changelog)

<br/>

---

<br/>

## Why HumanInk exists

LLMs write like LLMs. They inflate importance, dodge simple verbs, pad sentences with filler, and slather everything in hollow enthusiasm. Most people can *feel* it. They just can't name what's wrong.

**HumanInk names it, scores it, reports it, then kills it.**

Built on research from [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) and extended with 11 additional patterns from community observation. Used by writers, students, marketers, and developers who want their AI-assisted text to read like it was written by a human.

<br/>

## Features — What HumanInk does

| Feature | Description |
|---------|-------------|
| **AI Score (0-100)** | Quantified AI probability before and after rewriting |
| **35 AI writing patterns** | Full catalog of LLM writing tells — the most comprehensive open-source list |
| **Pattern report** | Detailed breakdown: which patterns, how many, where |
| **Context modes** | `--academic` `--casual` `--corporate` `--creative` `--general` |
| **Severity levels** | `--light` `--medium` `--aggressive` |
| **Diff output** | See exactly what changed with `--diff` |
| **Skip regions** | Protect text blocks with `<!-- humanink:skip -->` |
| **Style fingerprint** | Feed your own writing samples, get output that sounds like *you* |
| **Multi-language** | AI pattern detection in 7 languages with calibrated scoring |
| **Language shortcuts** | `--pt` and `--es` to force language mode directly |
| **Explain mode** | `--explain` adds inline annotations showing *why* each change was made |
| **Claude.ai compatible** | Works as Claude Code skill or Claude.ai Project skill |
| **Context-aware scoring** | Severity adjusts per mode — academic text isn't penalized for "Additionally" |
| **Model signatures** | Identifies ChatGPT vs Claude vs Gemini pattern clusters |
| **Paragraph scoring** | Per-paragraph breakdown shows *where* AI crept in |
| **Confidence indicator** | High/Medium/Low confidence based on unique pattern count |
| **Rewrite guardrails** | Prevents over-correction — preserves facts, word count, intent |

<br/>

## How HumanInk detects AI writing patterns

```
                         ┌──────────────┐
    Your text ──────────>│  Parse flags  │
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  AI Score    │──────> Score: 73/100 (Likely AI)
                         │  (0-100)     │
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  35-pattern  │──────> Pattern report
                         │  scan        │        (#7 AI vocab ×6, #1 inflation ×3...)
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  Rewrite     │──────> Draft (mode + severity applied)
                         │  + voice     │
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  Anti-AI     │──────> "What still screams AI?"
                         │  audit       │
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  Re-score    │──────> Score: 73 → 8 (-65)
                         └──────┬───────┘
                                │
                         ┌──────v───────┐
                         │  Deliver     │──────> Final version + report + diff
                         └──────────────┘
```

<br/>

## Quick start / Installation

**Install (one command):**

```bash
mkdir -p ~/.claude/skills && git clone https://github.com/sirambrosio/humanink.git ~/.claude/skills/humanink
```

**Use in Claude Code:**

```
/humanink

[paste your text]
```

**With flags:**

```
/humanink --casual --aggressive --diff --report

[paste your text]
```

**Update to latest version:**

```bash
cd ~/.claude/skills/humanink && git pull
```

<details>
<summary><b>Claude.ai (Projects) installation</b></summary>
<br/>

1. Download or ZIP the `humanink` folder
2. Go to Claude.ai → Projects → Project Knowledge
3. Upload the files (`SKILL.md`, `PATTERNS.md`, `STYLEGUIDE.md`)
4. Use `/humanink` in chat

</details>

<br/>

---

<br/>

## AI probability score system

Every text gets a score from 0 to 100 before and after rewriting. The algorithm uses pattern count, severity weights, density multiplier, context-aware adjustment, overlap correction, and a confidence indicator.

```
╔══════════════════════════════════╗
║  AI SCORE: 73 → 8  (-65)       ║
║  Status: Human                   ║
╚══════════════════════════════════╝
```

| Score | Label | Meaning |
|:-----:|-------|---------|
| 0-15 | **Human** | No significant AI patterns detected |
| 16-35 | **Mostly human** | Minor traces, could be coincidental |
| 36-55 | **Mixed** | Noticeable AI patterns, needs editing |
| 56-75 | **Likely AI** | Clear AI signatures throughout the text |
| 76-100 | **AI slop** | Unmistakably machine-generated content |

Paragraph-level scoring shows which sections are AI-written vs human-written — useful for detecting mixed-authorship documents. See [PATTERNS.md](PATTERNS.md) for pattern details and SKILL.md for the full scoring algorithm with a worked example.

<br/>

---

<br/>

## Context modes and flags

### Writing context modes

Choose one to match your writing context. Each mode adjusts pattern severity — for example, academic mode won't penalize "Additionally" since it's standard in papers.

| Flag | Tone | Best for |
|------|------|----------|
| `--general` | Balanced, natural (default) | Most text |
| `--academic` | Formal, precise, citations preserved | Papers, research, essays |
| `--casual` | Loose, contractions, first person | Blog posts, social media |
| `--corporate` | Clean, confident, professional | Reports, decks, emails |
| `--creative` | Maximum voice, edge, rule-breaking | Essays, opinion pieces |

### Severity levels

| Flag | What it does |
|------|-------------|
| `--light` | Fix only the worst offenders (severity 8-10) |
| `--medium` | Fix all clear AI patterns (default) |
| `--aggressive` | Full rewrite, restructure, maximize human voice |

### Output options

| Flag | What it adds |
|------|-------------|
| `--diff` | Shows removed/added text in diff format |
| `--report` | Full pattern report with counts and locations |
| `--score` | Score only, skip the rewrite |
| `--no-audit` | Skip second-pass audit (faster) |
| `--explain` | Inline annotations explaining *why* each change was made |
| `--pt` | Force Portuguese mode (skip auto-detection) |
| `--es` | Force Spanish mode (skip auto-detection) |

### Special features

| Feature | How to use |
|---------|-----------|
| **Skip regions** | Wrap text in `<!-- humanink:skip -->` ... `<!-- humanink:end -->` |
| **Style fingerprint** | Use `--style` then paste your own writing samples first |

<br/>

---

<br/>

## Before / After — Real example

<table>
<tr>
<th width="50%">
<p align="center">INPUT &nbsp; <code>AI Score: 78</code></p>
</th>
<th width="50%">
<p align="center">OUTPUT &nbsp; <code>AI Score: 6</code></p>
</th>
</tr>
<tr>
<td valign="top">

> Great question! Let's dive in and explore this topic. I hope this helps!
>
> AI-assisted coding serves as an enduring testament to the transformative potential of large language models, marking a pivotal moment in the evolution of software development. In today's rapidly evolving technological landscape, these groundbreaking tools — nestled at the intersection of research and practice — are reshaping how engineers ideate, iterate, and deliver, underscoring their vital role in modern workflows.
>
> At its core, the value proposition is clear: streamlining processes, enhancing collaboration, and fostering alignment. It's not just about autocomplete; it's about unlocking creativity at scale.
>
> - :bulb: **Speed:** Code generation is significantly faster.
> - :rocket: **Quality:** Output quality has been enhanced.
> - :white_check_mark: **Adoption:** Usage continues to grow, reflecting broader trends.
>
> In conclusion, the future looks bright. Exciting times lie ahead!

</td>
<td valign="top">

> AI coding assistants can speed up the boring parts of the job. They're great at boilerplate: config files and the glue code you don't want to write. They can also help you sketch a test, but you still have to read it.
>
> The dangerous part is how confident the suggestions look. I've accepted code that compiled and passed lint, then discovered later it missed the point because I stopped paying attention.
>
> If you treat it like autocomplete and review every line, it's useful. If you use it to avoid thinking, it will help you ship bugs faster.
>
> The only real backstop is tests. Without them, you're mostly judging vibes.

</td>
</tr>
<tr>
<td align="center">
<sub>15 pattern instances found across 11 patterns</sub>
</td>
<td align="center">
<sub>0 patterns remaining · AI Score dropped 72 points</sub>
</td>
</tr>
</table>

<br/>

---

<br/>

## 35 AI writing patterns detected

The most comprehensive open-source catalog of AI writing tells. Each pattern includes detection triggers, severity weights, before/after examples, and cross-language equivalents.

<details>
<summary><b>Content patterns</b> &nbsp; <code>#1-6</code></summary>
<br/>

| # | Pattern | Sev | AI tells |
|:---:|---------|:---:|----------|
| 1 | **Significance inflation** | 9 | "marking a pivotal moment in the evolution of..." |
| 2 | **Notability name-dropping** | 7 | "cited in NYT, BBC, FT, and The Hindu" |
| 3 | **Superficial -ing analyses** | 8 | "symbolizing... reflecting... showcasing..." |
| 4 | **Promotional language** | 8 | "nestled within the breathtaking region" |
| 5 | **Vague attributions** | 7 | "Experts believe it plays a crucial role" |
| 6 | **Formulaic challenges** | 6 | "Despite challenges... continues to thrive" |

</details>

<details>
<summary><b>Language patterns</b> &nbsp; <code>#7-12</code></summary>
<br/>

| # | Pattern | Sev | AI tells |
|:---:|---------|:---:|----------|
| 7 | **AI vocabulary** | 9 | "Additionally... testament... landscape..." |
| 8 | **Copula avoidance** | 7 | "serves as... features... boasts" |
| 9 | **Negative parallelisms** | 6 | "It's not just X, it's Y" |
| 10 | **Rule of three** | 5 | "innovation, inspiration, and insights" |
| 11 | **Synonym cycling** | 6 | "protagonist... main character... hero..." |
| 12 | **False ranges** | 5 | "from the Big Bang to dark matter" |

</details>

<details>
<summary><b>Style patterns</b> &nbsp; <code>#13-18</code></summary>
<br/>

| # | Pattern | Sev | AI tells |
|:---:|---------|:---:|----------|
| 13 | **Em dash abuse** | 5 | "this — and that — yet also —" |
| 14 | **Bold overuse** | 4 | "**OKRs**, **KPIs**, **BMC**" |
| 15 | **Inline-header lists** | 6 | "**Performance:** Performance improved" |
| 16 | **Title Case headings** | 4 | "Strategic Negotiations And Partnerships" |
| 17 | **Emojis in pro text** | 5 | ":rocket: Launch: :bulb: Insight:" |
| 18 | **Curly quotes** | 3 | \u201clike this\u201d |

</details>

<details>
<summary><b>Communication & filler patterns</b> &nbsp; <code>#19-24</code></summary>
<br/>

| # | Pattern | Sev | AI tells |
|:---:|---------|:---:|----------|
| 19 | **Chatbot artifacts** | 10 | "I hope this helps! Let me know..." |
| 20 | **Cutoff disclaimers** | 8 | "While details are limited..." |
| 21 | **Sycophantic tone** | 9 | "Great question! Absolutely!" |
| 22 | **Filler phrases** | 6 | "In order to", "Due to the fact that" |
| 23 | **Excessive hedging** | 7 | "could potentially possibly" |
| 24 | **Generic conclusions** | 8 | "The future looks bright" |

</details>

<details>
<summary><b>Extended patterns</b> &nbsp; <code>#25-35</code></summary>
<br/>

| # | Pattern | Sev | AI tells |
|:---:|---------|:---:|----------|
| 25 | **"In today's world" openers** | 8 | "In today's rapidly evolving landscape..." |
| 26 | **Dead metaphors** | 6 | "double-edged sword", "tip of the iceberg" |
| 27 | **"Meanwhile" transitions** | 5 | Overuse of "Meanwhile", "That said", "On the other hand" |
| 28 | **Mirror conclusions** | 7 | Conclusion paraphrases the introduction |
| 29 | **Uniform paragraph length** | 6 | Every paragraph is exactly 3 sentences |
| 30 | **"It is worth noting" hedges** | 7 | "It should be noted that...", "It bears mentioning..." |
| 31 | **Exhaustive list syndrome** | 6 | 8-item lists where 3 items would do |
| 32 | **Rubber stamp qualifiers** | 5 | "significant", "notable", "remarkable" as filler |
| 33 | **"Let's dive in" opener** | 8 | "Let's dive in", "Let's explore", "Without further ado" |
| 34 | **Bullet-heavy formatting** | 5 | >50% content in bullets where prose fits better |
| 35 | **Unnecessary numbered steps** | 5 | Numbered steps for things that aren't procedures |

</details>

<br/>

> Full pattern documentation with detection triggers, before/after examples, cross-language equivalents, and scoring weights: **[PATTERNS.md](PATTERNS.md)**

<br/>

---

<br/>

## Style fingerprint — Write in your voice

Feed HumanInk samples of your own writing. It analyzes your sentence length, vocabulary, punctuation habits, paragraph rhythm, and tone — then rewrites AI text in *your* voice.

```
/humanink --style

[paste 2-3 samples of your writing, minimum 200 words]
[then paste the text you want rewritten]
```

```
╔══════════════════════════════════════╗
║  VOICE PROFILE                       ║
╠══════════════════════════════════════╣
║  Sentences: short-medium (avg 14w)   ║
║  Variance: high (SD 6.2)            ║
║  Contractions: always               ║
║  Vocabulary: mid-level, some jargon ║
║  Humor: dry, infrequent             ║
║  Directness: high                   ║
╚══════════════════════════════════════╝
```

> Full voice analysis framework: **[STYLEGUIDE.md](STYLEGUIDE.md)**

<br/>

---

<br/>

## Multi-language AI detection

The 35 AI writing patterns are universal across languages. HumanInk detects language automatically and maps patterns to local equivalents. Use `--pt` or `--es` to skip detection and force a language.

Supported languages: English, Portuguese, Spanish, French, German, Japanese, Italian.

<details>
<summary><b>See language-specific AI tells</b></summary>
<br/>

| Language | Common AI tells |
|----------|----------------|
| :brazil: Portuguese | "Adicionalmente", "destaca-se", "fomentar", "paisagem" (abstract), "No mundo atual" |
| :es: Spanish | "Adicionalmente", "panorama", "destacar", "fomentar", "En el mundo actual" |
| :fr: French | "De plus", "mettre en lumiere", "au coeur de", "Dans le monde d'aujourd'hui" |
| :de: German | "Daruber hinaus", "entscheidend", "Landschaft" (abstract), stacked subordinate clauses |
| :jp: Japanese | Overuse of "において", excessive "という" nominalizations, "さらに" |
| :it: Italian | "Inoltre", "sottolineare", "panorama", "nell'ambito di" |

Scoring thresholds adapt per language — em dashes score lower in Portuguese (where they're common), formal register scores differently in academic Japanese, etc.

</details>

<br/>

---

<br/>

## Model signature detection — ChatGPT vs Claude vs Gemini

HumanInk identifies which AI model likely generated the text based on pattern clusters:

| Model | Signature patterns | Common tells |
|-------|-------------------|--------------|
| **ChatGPT** | Formatting-heavy (#14, #15, #17, #34) | Bold overuse, emoji lists, bullet-heavy output |
| **Claude** | Hedging-heavy (#22, #23, #30) | Excessive qualifiers, "It's worth noting", over-cautious tone |
| **Gemini** | Inflation-heavy (#1, #4, #25) | "In today's world", promotional language, significance inflation |

Model detection is reported as a hint, not a definitive claim — patterns overlap between models.

<br/>

---

<br/>

## Project structure

```
humanink/
├── SKILL.md         ← core skill definition (source of truth)
├── PATTERNS.md      ← 35 patterns: triggers, examples, cross-language, scoring
├── STYLEGUIDE.md    ← voice fingerprint framework
├── WARP.md          ← guidance for Warp terminal
└── README.md        ← you are here
```

No runtime. No dependencies. No build step. No API keys. Pure Markdown.
Works as a Claude Code skill or Claude.ai Project skill.

<br/>

---

<br/>

## FAQ

<details>
<summary><b>Does HumanInk work with ChatGPT or other LLMs?</b></summary>
<br/>

HumanInk is designed as a skill for **Claude Code** and **Claude.ai**. It doesn't work with ChatGPT directly. However, the pattern catalog in [PATTERNS.md](PATTERNS.md) is model-agnostic — you can use it as a reference to manually identify AI patterns in any text.

</details>

<details>
<summary><b>Will this bypass AI detectors like GPTZero, Turnitin, or Originality.ai?</b></summary>
<br/>

HumanInk rewrites text to remove recognizable AI patterns and match human writing characteristics. The result reads more naturally because it *is* more natural — not because it's "tricking" a detector. The focus is on writing quality, not detection evasion.

</details>

<details>
<summary><b>Can I use this for academic work?</b></summary>
<br/>

Use `--academic` mode. It preserves citations, formal register, and field-specific terminology while removing the robotic patterns that make AI-assisted text obvious. Always follow your institution's AI usage policies.

</details>

<details>
<summary><b>How is this different from Undetectable AI, QuillBot, etc.?</b></summary>
<br/>

Those are paid SaaS tools that paraphrase text. HumanInk is different:
- **Open source** and free forever
- **Transparent** — you can read every pattern and scoring rule
- **No API** — runs entirely inside Claude as a skill
- **Style-aware** — can replicate *your* voice, not just generic "human" text
- **Educational** — `--explain` mode teaches you *why* each pattern is AI-like

</details>

<details>
<summary><b>Does it work in languages other than English?</b></summary>
<br/>

Yes. HumanInk supports 7 languages: English, Portuguese, Spanish, French, German, Japanese, and Italian. Each language has calibrated scoring thresholds and localized AI pattern equivalents.

</details>

<br/>

---

<br/>

## Contributing

Contributions are welcome. Here's how you can help:

- **Report a new AI pattern** — found a pattern not in the list? Open an issue with examples
- **Add language support** — extend cross-language equivalents in [PATTERNS.md](PATTERNS.md)
- **Improve detection** — suggest better triggers or before/after examples
- **Fix bugs** — found a scoring edge case? Submit a PR

See [WARP.md](WARP.md) for the full guide on adding patterns and editing files.

<br/>

---

<br/>

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — primary source for patterns 1-24
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — the team maintaining the guide
- Patterns 25-35 sourced from community observation and extended research

> *"LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."* — Wikipedia

<br/>

## Changelog

| Version | What changed |
|---------|-------------|
| **2.2.0** | Context-aware severity (per mode), model signatures (ChatGPT/Claude/Gemini), paragraph-level scoring, confidence indicator, rewrite guardrails, co-occurrence detection, Italian language support, worked scoring example |
| **2.1.0** | 35 patterns (#33-#35 new), `--pt`/`--es` language shortcuts, `--explain` mode, Claude.ai compatibility, overlap scoring groups, threshold gating |
| **2.0.0** | AI score system, 32 patterns (8 new), pattern report, context modes, severity levels, diff output, skip regions, style fingerprint, multi-language calibration |
| **1.0.0** | Initial release. 24 patterns, two-pass audit. |

<br/>

---

<br/>

<p align="center">
  <strong>HumanInk</strong>
  <br/>
  <sub>by <a href="https://github.com/sirambrosio">Andre Ambrosio</a></sub>
  <br/>
  <br/>
  <sub>If a machine wrote it, a machine can un-write it.</sub>
  <br/>
  <br/>
  <a href="LICENSE"><img src="https://img.shields.io/badge/MIT-111?style=flat-square" alt="MIT" /></a>
  &nbsp;
  <a href="https://github.com/sirambrosio/humanink/stargazers"><img src="https://img.shields.io/github/stars/sirambrosio/humanink?style=flat-square" alt="stars" /></a>
</p>
