# Contributing to HumanInk

Thanks for wanting to make AI-generated text less obvious.

## What we need

- **New patterns** — found a new AI writing tell? Open an issue describing it.
- **False positives** — a pattern flagging human text incorrectly? Show us the example.
- **Language support** — HumanInk currently supports EN, PT, ES, FR, DE, JA, IT. More welcome.
- **Style fingerprints** — examples of distinct human writing styles to improve rewriting quality.

## How to contribute

1. Fork the repo
2. Create a branch: `git checkout -b pattern/your-pattern-name`
3. Make your changes in the relevant `.md` file
4. Open a PR with a clear description and one or two real-world examples

## Pattern format (PATTERNS.md)

Each pattern entry should include:

```
### Pattern Name
- **What it is:** short description
- **Why it's AI:** explanation of why models produce this
- **Example (AI):** "..."
- **Example (Human):** "..."
- **Score impact:** +N points
```

## Questions?

Open a Discussion — not an issue. Issues are for bugs and concrete proposals.

## Code of conduct

Be direct. No fluff. Ironic, given the project.
