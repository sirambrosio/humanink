# HumanInk — Style fingerprint guide

This file defines how HumanInk analyzes and replicates a user's personal writing style when `--style` mode is activated.

---

## How style fingerprinting works

Instead of rewriting to a generic "human" voice, style fingerprinting makes the output sound like *you*.

### Step 1: Collect samples

When `--style` is invoked, ask the user to provide 2-3 samples of their natural writing. Minimum 200 words total. Best sources:

- Personal blog posts
- Casual emails or Slack messages
- Social media posts they wrote themselves
- Internal memos or reports
- Any text they feel represents "their voice"

### Step 2: Analyze voice dimensions

Extract these metrics from the samples:

#### Sentence architecture
| Metric | What to measure |
|--------|----------------|
| Average length | Words per sentence (short: 8-12, medium: 13-18, long: 19+) |
| Length variance | Standard deviation — high variance = more human feel |
| Fragment usage | Does the writer use sentence fragments? How often? |
| Max sentence length | Longest sentence — indicates comfort with complexity |
| Opening patterns | How do they start sentences? Subject-first? Conditional? |

#### Vocabulary profile
| Metric | What to measure |
|--------|----------------|
| Complexity | Simple vs. advanced vocabulary (Flesch-Kincaid proxy) |
| Jargon comfort | Do they use industry terms freely or explain them? |
| Contraction rate | "don't/can't" vs. "do not/cannot" — ratio matters |
| Profanity/slang | Any casual language? Level of informality? |
| Favorite words | Words that appear at higher-than-average rates |

#### Punctuation habits
| Metric | What to measure |
|--------|----------------|
| Semicolons | Frequent, rare, or never? |
| Dashes | Em dashes, en dashes, hyphens — usage pattern |
| Parentheses | Asides in parentheses? How often? |
| Ellipses | "..." usage — thinking pauses? |
| Exclamation marks | Frequency and context |
| Comma density | Heavy or minimal comma usage |

#### Paragraph structure
| Metric | What to measure |
|--------|----------------|
| Average length | Sentences per paragraph |
| Length variance | Does paragraph length vary? |
| One-liners | Do they use single-sentence paragraphs? |
| Transition style | How do they connect paragraphs? Explicit connectors or implicit? |

#### Tone markers
| Metric | What to measure |
|--------|----------------|
| Humor | Present? What kind? Dry, sarcastic, self-deprecating? |
| Directness | Do they hedge or state things bluntly? |
| First person | "I" frequency — high, medium, low? |
| Reader address | Do they address "you" directly? |
| Rhetorical questions | Used for emphasis? Frequency? |
| Emotional range | Do they express feelings openly? |
| Confidence level | Assertive statements vs. qualified claims |

### Step 3: Build voice profile

Compile findings into a compact profile:

```
╔══════════════════════════════════════╗
║  VOICE PROFILE                       ║
╠══════════════════════════════════════╣
║  Sentences: short-medium (avg 14w)   ║
║  Variance: high (SD 6.2)            ║
║  Fragments: occasional              ║
║  Contractions: always               ║
║  Vocabulary: mid-level, some jargon ║
║  Semicolons: never                  ║
║  Dashes: moderate                   ║
║  Paragraphs: varied (1-6 sentences) ║
║  Humor: dry, infrequent             ║
║  First person: heavy                ║
║  Directness: high                   ║
║  Rhetorical Qs: occasional          ║
╚══════════════════════════════════════╝
```

### Step 4: Apply during rewrite

When rewriting with a voice profile active:

1. **Match sentence length distribution** — don't just match the average, match the *variance*. If the user writes both 5-word and 30-word sentences, do the same.

2. **Mirror vocabulary level** — if they use simple words, don't upgrade. If they use technical terms without explanation, do the same.

3. **Copy punctuation habits** — if they never use semicolons, neither should the output. If they love parenthetical asides, include them.

4. **Replicate paragraph rhythm** — match their pattern of short/long paragraphs, not a uniform rhythm.

5. **Preserve tone** — if they're blunt, be blunt. If they hedge naturally, allow some hedging (but not AI-style hedging).

6. **Use their words** — if the sample shows they prefer "stuff" over "material" or "thing" over "artifact", honor that.

---

## Voice archetypes

When no `--style` samples are provided, HumanInk defaults to the selected context mode. Each mode has a baseline voice:

### --general (default)
```
Sentences: medium (avg 15w)
Variance: moderate
Contractions: frequent
Vocabulary: accessible
Tone: direct, neutral-warm
First person: occasional
Humor: rare
```

### --academic
```
Sentences: medium-long (avg 20w)
Variance: moderate
Contractions: rare
Vocabulary: field-appropriate
Tone: measured, precise
First person: discipline-dependent
Humor: very rare
Hedging: appropriate (not excessive)
```

### --casual
```
Sentences: short-medium (avg 12w)
Variance: high
Fragments: welcome
Contractions: always
Vocabulary: simple, colloquial
Tone: loose, friendly
First person: heavy
Humor: welcome
```

### --corporate
```
Sentences: medium (avg 16w)
Variance: moderate
Contractions: moderate
Vocabulary: business-appropriate, no jargon soup
Tone: confident, clear
First person: "we" over "I"
Humor: very rare, if ever
```

### --creative
```
Sentences: any length
Variance: maximum
Fragments: encouraged
Contractions: natural
Vocabulary: anything goes
Tone: distinctive, opinionated
First person: whatever fits
Humor: whatever fits
Rules: break them if it serves the writing
```

---

## Quality checks

After applying a voice profile, verify:

1. **Read aloud test** — does it sound like one person wrote it?
2. **Consistency test** — is the voice stable throughout, not shifting between paragraphs?
3. **Authenticity test** — would the user recognize this as something they might have written?
4. **Pattern test** — did the voice application accidentally reintroduce any AI patterns?

If any check fails, revise before delivering.

---

## Combining with other modes

### --style + --explain

When both `--style` and `--explain` are active, annotations should reference the voice profile:

```
[rewritten paragraph]
  ↳ Changed because: #7 AI vocabulary. Replaced "Additionally" with "Also" — matches your contraction-heavy, direct style (voice profile: directness=high).
```

This teaches the user not just *what* was AI, but *how* their personal voice differs from the AI default.

### --style + --pt / --es

When combined with language shortcuts, the voice analysis adapts to language-specific norms. Portuguese writers naturally use longer sentences and more gerunds — the voice profile calibrates accordingly so style replication doesn't fight the language's grain.

---

*HumanInk Style Guide — your voice, not a generic "human" one.*
