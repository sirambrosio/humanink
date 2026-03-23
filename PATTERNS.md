# HumanInk — Pattern catalog

Complete reference for all 35 AI writing patterns detected by HumanInk. Each pattern includes detection rules, severity weight, before/after examples, and cross-language equivalents.

---

## Severity scale

| Weight | Level | Meaning |
|--------|-------|---------|
| 1-3 | Low | Minor tell, could be human |
| 4-6 | Medium | Noticeable AI pattern |
| 7-8 | High | Strong AI signal |
| 9-10 | Critical | Unmistakable AI signature |

---

## Content patterns

### #1 — Significance inflation
**Severity: 9** | **Category: Content**

LLMs inflate the importance of everything. A simple fact becomes "a pivotal moment in the evolution of." Kill the inflation, keep the fact.

**Detection triggers:**
stands/serves as, is a testament/reminder, a vital/significant/crucial/pivotal/key role/moment, underscores/highlights its importance/significance, reflects broader, symbolizing its ongoing/enduring/lasting, contributing to the, setting the stage for, marking/shaping the, represents/marks a shift, key turning point, evolving landscape, focal point, indelible mark, deeply rooted

**Before:**
> The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. This initiative was part of a broader movement across Spain to decentralize administrative functions and enhance regional governance.

**After:**
> The Statistical Institute of Catalonia was established in 1989 to collect and publish regional statistics independently from Spain's national office.

**Cross-language triggers:**
| Language | Equivalents |
|----------|------------|
| Portuguese | "marcando um momento crucial", "servindo como um testemunho", "papel fundamental", "destaca a importância" |
| Spanish | "representando un hito fundamental", "papel crucial/clave", "subraya la importancia" |
| French | "marquant un tournant décisif", "témoignage de", "rôle crucial/clé" |
| German | "markiert einen Wendepunkt", "Zeugnis für", "unterstreicht die Bedeutung" |
| Italian | "segnando un momento cruciale", "testimonianza di", "ruolo fondamentale" |
| Japanese | "における画期的な", "重要な役割を果たす", "の重要性を浮き彫りにする" |

---

### #2 — Notability name-dropping
**Severity: 7** | **Category: Content**

LLMs list media sources like a résumé. No context, just credibility stacking.

**Detection triggers:**
independent coverage, local/regional/national media outlets, written by a leading expert, active social media presence, has been featured in, covered by, recognized by

**Before:**
> Her views have been cited in The New York Times, BBC, Financial Times, and The Hindu. She maintains an active social media presence with over 500,000 followers.

**After:**
> In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods.

---

### #3 — Superficial -ing analyses
**Severity: 8** | **Category: Content**

LLMs tack "-ing" phrases onto sentences to fake analytical depth. It's the written equivalent of nodding wisely while saying nothing.

**Detection triggers:**
highlighting/underscoring/emphasizing..., ensuring..., reflecting/symbolizing..., contributing to..., cultivating/fostering..., encompassing..., showcasing..., demonstrating..., illustrating...

**Before:**
> The temple's color palette of blue, green, and gold resonates with the region's natural beauty, symbolizing Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes, reflecting the community's deep connection to the land.

**After:**
> The temple uses blue, green, and gold. The architect said these were chosen to reference local bluebonnets and the Gulf coast.

**Cross-language note:**
In Romance languages this manifests as gerunds (PT: "-ando/-endo", ES: "-ando/-iendo", FR: "-ant"). In German, it shows up as stacked subordinate clauses. In Japanese, excessive use of "ことで" (koto de) and "ながら" (nagara) chains.

---

### #4 — Promotional language
**Severity: 8** | **Category: Content**

LLMs can't stay neutral. Everything is "vibrant" and "nestled" and "breathtaking."

**Detection triggers:**
boasts a, vibrant, rich (figurative), profound, enhancing its, showcasing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking (figurative), renowned, breathtaking, must-visit, stunning, world-class, cutting-edge, state-of-the-art

**Before:**
> Nestled within the breathtaking region of Gonder in Ethiopia, Alamata stands as a vibrant town with a rich cultural heritage and stunning natural beauty.

**After:**
> Alamata is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.

**Cross-language triggers:**
| Language | Equivalents |
|----------|------------|
| Portuguese | "aninhado", "vibrante", "rico patrimônio", "deslumbrante", "de tirar o fôlego" |
| Spanish | "ubicado en el corazón de", "vibrante", "impresionante", "de vanguardia" |
| French | "niché au cœur de", "vibrant", "époustouflant", "incontournable" |
| German | "eingebettet in", "lebhaft", "atemberaubend", "bahnbrechend" |

---

### #5 — Vague attributions
**Severity: 7** | **Category: Content**

LLMs attribute opinions to ghosts. "Experts believe" — which experts?

**Detection triggers:**
Industry reports, Observers have cited, Experts argue/believe, Some critics argue, several sources/publications, widely regarded, generally considered, many people think, research suggests (without citation)

**Before:**
> Due to its unique characteristics, the river is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.

**After:**
> The river supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.

---

### #6 — Formulaic challenges sections
**Severity: 6** | **Category: Content**

The "challenges" paragraph is an LLM reflex. Vague problems, vague optimism, zero information.

**Detection triggers:**
Despite its... faces several challenges..., Despite these challenges, Challenges and Legacy, Future Outlook, remains to be seen, faces unique challenges, poised for growth

**Before:**
> Despite its industrial prosperity, Korattur faces challenges typical of urban areas, including traffic congestion and water scarcity. Despite these challenges, Korattur continues to thrive as an integral part of Chennai's growth.

**After:**
> Traffic congestion increased after 2015 when three new IT parks opened. The municipality began a drainage project in 2022 to address recurring floods.

---

## Language patterns

### #7 — AI vocabulary
**Severity: 9** | **Category: Language**

These words appear at 10x their normal rate in post-2023 text. Two or more in one paragraph = suspect.

**Detection triggers:**
Additionally, align with, at its core, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate/intricacies, key (adjective), landscape (abstract noun), leveraging, multifaceted, navigate (abstract), nuanced, pivotal, realm, robust, seamless, showcase, streamline, tapestry (abstract noun), testament, underscore (verb), valuable, vibrant

**Before:**
> Additionally, a distinctive feature of Somali cuisine is the incorporation of camel meat. An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**After:**
> Somali cuisine also includes camel meat, considered a delicacy. Pasta, introduced during Italian colonization, remains common in the south.

**Cross-language triggers:**
| Language | Equivalents |
|----------|------------|
| Portuguese | "Adicionalmente", "crucial", "paisagem" (abstract), "destaca-se", "fomentar", "robusto", "multifacetado", "navegar" (abstract) |
| Spanish | "Adicionalmente", "crucial", "panorama", "destacar", "fomentar", "robusto", "navegar" (abstract) |
| French | "De plus", "crucial", "paysage" (abstract), "mettre en lumière", "favoriser", "robuste" |
| German | "Darüber hinaus", "entscheidend", "Landschaft" (abstract), "unterstreichen", "fördern", "robust" |
| Japanese | "さらに" (overuse), "重要な", "～の風景" (abstract), "～を浮き彫りにする", "促進する" |

---

### #8 — Copula avoidance
**Severity: 7** | **Category: Language**

LLMs avoid "is" and "has" like they're being charged per use.

**Detection triggers:**
serves as, stands as, marks, represents [a], boasts, features, offers [a], functions as, operates as, acts as (when "is" would work)

**Before:**
> Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces and boasts over 3,000 square feet.

**After:**
> Gallery 825 is LAAA's exhibition space for contemporary art. It has four rooms totaling 3,000 square feet.

---

### #9 — Negative parallelisms
**Severity: 6** | **Category: Language**

**Detection triggers:**
Not only...but..., It's not just about..., it's..., It's not merely..., it's..., It isn't just..., It goes beyond...

**Before:**
> It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.

**After:**
> The heavy beat adds to the aggressive tone.

---

### #10 — Rule of three
**Severity: 5** | **Category: Language**

LLMs force ideas into triplets. Real text uses whatever number fits.

**Detection triggers:**
Three-item lists that feel forced, especially with abstract nouns. Watch for: "X, Y, and Z" where all three are near-synonyms or padding.

**Before:**
> The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.

**After:**
> The event includes talks and panels. There's also time for networking between sessions.

---

### #11 — Synonym cycling
**Severity: 6** | **Category: Language**

LLMs have repetition penalties that cause excessive synonym substitution.

**Before:**
> The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.

**After:**
> The protagonist faces many challenges but eventually triumphs and returns home.

---

### #12 — False ranges
**Severity: 5** | **Category: Language**

**Detection triggers:**
"from X to Y" where X and Y aren't on a meaningful scale.

**Before:**
> Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**After:**
> The book covers the Big Bang, star formation, and current theories about dark matter.

---

## Style patterns

### #13 — Em dash abuse
**Severity: 5** | **Category: Style**

LLMs overuse em dashes (—) to sound punchy. Real writing uses commas and periods.

**Note:** Em dashes are more common in some languages (Portuguese, Spanish) and publications. Adjust threshold by context.

**Before:**
> The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues—even in official documents.

**After:**
> The term is primarily promoted by Dutch institutions, not by the people themselves. This mislabeling persists in official documents.

---

### #14 — Bold overuse
**Severity: 4** | **Category: Style**

LLMs bold things mechanically. If everything is emphasized, nothing is.

**Before:**
> It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)** and **Balanced Scorecard (BSC)**.

**After:**
> It blends OKRs, KPIs, and visual strategy tools like the Business Model Canvas and Balanced Scorecard.

---

### #15 — Inline-header lists
**Severity: 6** | **Category: Style**

AI loves bullets where every item starts with a bolded label and colon. Convert to prose.

**Before:**
> - **User Experience:** The user experience has been significantly improved with a new interface.
> - **Performance:** Performance has been enhanced through optimized algorithms.
> - **Security:** Security has been strengthened with end-to-end encryption.

**After:**
> The update improves the interface, speeds up load times through optimized algorithms, and adds end-to-end encryption.

---

### #16 — Title Case headings
**Severity: 4** | **Category: Style**

**Before:**
> ## Strategic Negotiations And Global Partnerships

**After:**
> ## Strategic negotiations and global partnerships

---

### #17 — Emojis in professional text
**Severity: 5** | **Category: Style**

Remove unless context genuinely calls for it (social media, casual chat).

**Before:**
> 🚀 **Launch Phase:** The product launches in Q3
> 💡 **Key Insight:** Users prefer simplicity

**After:**
> The product launches in Q3. User research showed a preference for simplicity.

---

### #18 — Curly quotes
**Severity: 3** | **Category: Style**

ChatGPT uses curly quotes (\u201c...\u201d) instead of straight quotes ("...").

**Before:**
> He said \u201cthe project is on track\u201d but others disagreed.

**After:**
> He said "the project is on track" but others disagreed.

---

## Communication patterns

### #19 — Chatbot artifacts
**Severity: 10** | **Category: Communication**

Text from a chatbot conversation pasted as content. Remove entirely.

**Detection triggers:**
I hope this helps, Of course!, Certainly!, You're absolutely right!, Would you like..., let me know, here is a..., Feel free to ask, I'd be happy to, Sure thing!, Happy to help

**Before:**
> Here is an overview of the French Revolution. I hope this helps! Let me know if you'd like me to expand on any section.

**After:**
> The French Revolution began in 1789 when financial crisis and food shortages led to widespread unrest.

---

### #20 — Knowledge-cutoff disclaimers
**Severity: 8** | **Category: Communication**

**Detection triggers:**
as of [date], Up to my last training update, While specific details are limited/scarce..., based on available information..., I don't have access to real-time..., as of my knowledge cutoff

**Before:**
> While specific details about the company's founding are not extensively documented in readily available sources, it appears to have been established sometime in the 1990s.

**After:**
> The company was founded in 1994, according to its registration documents.

---

### #21 — Sycophantic tone
**Severity: 9** | **Category: Communication**

**Detection triggers:**
Great question!, You're absolutely right!, That's an excellent point!, Absolutely!, What a wonderful/fascinating/insightful..., I love that idea!

**Before:**
> Great question! You're absolutely right that this is a complex topic. That's an excellent point about the economic factors.

**After:**
> The economic factors you mentioned are relevant here.

---

### #22 — Filler phrases
**Severity: 6** | **Category: Filler**

Kill on sight:

| Filler | Replacement |
|--------|-------------|
| In order to | To |
| Due to the fact that | Because |
| At this point in time | Now |
| In the event that | If |
| Has the ability to | Can |
| It is important to note that | (delete, just state it) |
| In terms of | (rewrite) |
| With regard to | About |
| For the purpose of | To/For |
| In light of the fact that | Because/Since |

---

### #23 — Excessive hedging
**Severity: 7** | **Category: Filler**

One qualifier per claim maximum.

**Before:**
> It could potentially possibly be argued that the policy might have some effect on outcomes.

**After:**
> The policy may affect outcomes.

---

### #24 — Generic positive conclusions
**Severity: 8** | **Category: Filler**

Vague optimistic endings are an LLM signature.

**Detection triggers:**
The future looks bright, Exciting times lie ahead, continue this journey toward excellence, poised for success, the possibilities are endless, only time will tell, one thing is certain, remains to be seen but

**Before:**
> The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence. This represents a major step in the right direction.

**After:**
> The company plans to open two more locations next year.

---

## Extended patterns

### #25 — "In today's world" openers
**Severity: 8** | **Category: Content**

LLMs open paragraphs with temporal padding that says nothing.

**Detection triggers:**
In today's world, In today's rapidly evolving, In the modern era, In an increasingly connected, In this day and age, In the current landscape, As we navigate, In an era of

**Before:**
> In today's rapidly evolving technological landscape, artificial intelligence has become an indispensable tool for businesses seeking to maintain a competitive edge.

**After:**
> Most large companies now use AI tools for at least one business function, according to McKinsey's 2024 survey.

**Cross-language triggers:**
| Language | Equivalents |
|----------|------------|
| Portuguese | "No mundo atual", "Na era moderna", "Em um cenário em constante evolução" |
| Spanish | "En el mundo actual", "En la era moderna", "En un panorama en constante cambio" |
| French | "Dans le monde d'aujourd'hui", "À l'ère du numérique" |
| German | "In der heutigen Welt", "Im Zeitalter der Digitalisierung" |

---

### #26 — Dead metaphors
**Severity: 6** | **Category: Language**

LLMs recycle the same metaphors because they're statistically common.

**Detection triggers:**
double-edged sword, tip of the iceberg, game-changer, paradigm shift, at the forefront, paving the way, the fabric of, a beacon of, a cornerstone of, the backbone of, a gateway to, the dawn of, a bridge between, tapestry of, mosaic of

**Before:**
> AI is a double-edged sword that represents the tip of the iceberg in terms of what's possible. This paradigm shift is paving the way for a new dawn of innovation.

**After:**
> AI tools create real tradeoffs. The automation gains come with new failure modes that most teams haven't figured out yet.

---

### #27 — "Meanwhile" transitions
**Severity: 5** | **Category: Language**

LLMs overuse "meanwhile" and similar transition words to connect unrelated paragraphs.

**Detection triggers:**
Meanwhile, On the other hand, Conversely, That said, Having said that, With that in mind, By the same token, Along those lines, In a similar vein

When these appear 3+ times in one text, it's a pattern.

**Before:**
> The company reported strong earnings. Meanwhile, the tech sector continues to evolve. On the other hand, some analysts remain cautious. That said, the outlook is positive.

**After:**
> The company reported strong earnings. Some analysts are cautious about the broader tech sector, but the fundamentals look solid.

---

### #28 — Mirror conclusions
**Severity: 7** | **Category: Content**

LLMs end by paraphrasing the introduction. Real writing moves forward.

**Detection triggers:**
Compare the first and last paragraphs. If the conclusion restates the intro with different words, it's a mirror. Also watch for: "In conclusion", "To summarize", "As we've seen", "All in all"

**Before:**
> *Intro:* AI tools are changing how developers write code.
> *Conclusion:* As we've seen, AI tools are fundamentally reshaping the way developers approach coding.

**After:**
> *Conclusion:* The question isn't whether to use AI tools. It's whether your team has the testing discipline to catch what they get wrong.

---

### #29 — Uniform paragraph length
**Severity: 6** | **Category: Style**

LLMs produce paragraphs of suspiciously similar length — typically 3 sentences each.

**Detection method:**
Measure sentence count per paragraph. If standard deviation is < 0.5 across 4+ paragraphs, flag it.

**Fix:** Vary deliberately. One-sentence paragraphs. Five-sentence paragraphs. Let content dictate length, not rhythm.

---

### #30 — "It is worth noting" hedges
**Severity: 7** | **Category: Filler**

Throat-clearing before making a point. Just make the point.

**Detection triggers:**
It is worth noting that, It is important to mention, It should be noted that, It bears mentioning, One cannot overlook, It is noteworthy that, It must be emphasized that, It goes without saying

**Before:**
> It is worth noting that the company's revenue increased by 40% last year. It should be noted that this growth was primarily driven by international expansion.

**After:**
> Revenue grew 40% last year, mostly from international expansion.

---

### #31 — Exhaustive list syndrome
**Severity: 6** | **Category: Content**

LLMs try to cover everything. Real experts pick the 2-3 things that matter most.

**Detection method:**
Lists with 5+ items where some are near-synonyms or padding. Sentences that try to enumerate every possible aspect.

**Before:**
> The framework supports modularity, scalability, flexibility, extensibility, maintainability, reusability, testability, and observability.

**After:**
> The framework is modular and scales well. Those were the main design goals.

---

### #32 — Rubber stamp qualifiers
**Severity: 5** | **Category: Language**

Empty adjectives that add no information.

**Detection triggers:**
significant, notable, remarkable, substantial, considerable, impressive, meaningful (when used as filler, not with specific reference)

**Before:**
> The company has made significant progress in achieving notable milestones, resulting in a remarkable increase in considerable market share.

**After:**
> Market share grew from 12% to 19% in 2024.

---

### #33 — "Let's dive in" opener
**Severity: 8** | **Category: Communication**

The classic AI invitation to the reader. Real writers don't announce they're about to start writing — they just start.

**Detection triggers:**
"Let's dive in", "Let's explore", "Let's break it down", "Let's take a closer look", "Let's unpack this", "Without further ado"

**Before:**
> Let's dive in and explore the key benefits of this approach.

**After:**
> Here's what works about this approach.

**Cross-language equivalents:**
- **PT:** "Vamos explorar", "Vamos mergulhar", "Sem mais delongas"
- **ES:** "Vamos a explorar", "Sin más preámbulos", "Profundicemos"
- **FR:** "Plongeons dans le sujet", "Explorons ensemble"
- **DE:** "Tauchen wir ein", "Schauen wir uns das genauer an"

---

### #34 — Bullet-heavy formatting
**Severity: 5** | **Category: Style**

AI loves converting flowing prose into bulleted lists, even when the content doesn't call for it. A paragraph with three related ideas becomes three disconnected bullets.

**Detection triggers:**
More than 50% of content in bulleted/numbered lists. Lists used where prose would flow better. Lists where items are full sentences that could form a paragraph.

**Before:**
> Key takeaways:
> - The project was completed on time
> - The budget remained within expectations
> - Team satisfaction scores improved
> - Client feedback was overwhelmingly positive

**After:**
> The project landed on time and under budget. The team liked the process, and the client was happy with the result.

**Cross-language equivalents:**
Universal pattern — AI in all languages over-relies on bullet formatting.

**Language-specific triggers:**
- **PT:** Listas com "•" ou "-" onde um parágrafo faria mais sentido
- **ES:** Viñetas con oraciones completas que funcionarían mejor como prosa
- **FR:** Listes à puces pour des idées qui coulent naturellement en paragraphe
- **DE:** Aufzählungen mit ganzen Sätzen, die als Fließtext besser wären
- **JA:** 箇条書きの多用（文章で書いた方が自然な場合）

---

### #35 — Unnecessary numbered steps
**Severity: 5** | **Category: Style**

AI turns simple instructions or descriptions into numbered step sequences, adding false procedural weight. Not everything is a "step-by-step guide."

**Detection triggers:**
Numbered steps for processes that are naturally flowing or have fewer than 3 genuine steps. Steps that are single sentences with no complexity.

**Before:**
> Here's how to make coffee:
> 1. First, fill the kettle with water
> 2. Then, boil the water
> 3. Next, add coffee grounds to your cup
> 4. Finally, pour the hot water over the grounds

**After:**
> Boil water, add grounds to the cup, pour. That's it.

**Cross-language equivalents:**
- **PT:** "Passo 1:", "Primeiro,", "Em seguida,", "Por fim,"
- **ES:** "Paso 1:", "Primero,", "A continuación,", "Finalmente,"
- **FR:** "Étape 1:", "Premièrement,", "Ensuite,", "Enfin,"
- **DE:** "Schritt 1:", "Zunächst,", "Anschließend,", "Abschließend,"

---

## Scoring weights reference

Quick reference for the AI score calculation:

| Severity | Points per instance | Patterns |
|----------|-------------------|----------|
| 10 | 10 pts | #19 |
| 9 | 8 pts | #1, #7, #21 |
| 8 | 6 pts | #3, #4, #20, #24, #25, #33 |
| 7 | 5 pts | #2, #5, #8, #23, #28, #30 |
| 6 | 3 pts | #6, #9, #11, #15, #22, #26, #29, #31 |
| 5 | 2 pts | #10, #12, #13, #17, #27, #32, #34, #35 |
| 4 | 1 pt | #14, #16 |
| 3 | 1 pt | #18 |

**Normalization:** Raw points are capped at 100. For texts under 100 words, multiply by density factor (patterns per 100 words).

For the complete scoring algorithm with threshold gating, overlap adjustment, and density multiplier, see the AI SCORE SYSTEM section in `SKILL.md`.

---

## Pattern overlap groups

Some patterns frequently co-occur. To avoid inflating the score, these groups have special scoring rules.

### Promotional cluster (#1, #4, #7)

Significance inflation, promotional language, and AI vocabulary frequently co-occur in descriptive/marketing text. A paragraph like "This vibrant initiative showcases the pivotal role of fostering innovation" triggers all three simultaneously.

**Scoring rule:** When all 3 appear in the same paragraph, count the highest-severity instance at full points and reduce others by 50%.

### Hedging cluster (#22, #23, #30)

Filler phrases, excessive hedging, and "worth noting" hedges co-occur in cautious AI text. Example: "It is worth noting that, in order to potentially address this issue..."

**Scoring rule:** When 2+ appear in the same sentence, count only the highest-severity instance.

### Chatbot cluster (#19, #20, #21, #33)

Chatbot artifacts, cutoff disclaimers, sycophantic tone, and "Let's dive in" openers appear together in raw chatbot output pasted as content. These are all critical signals and should be counted independently.

**Scoring rule:** Count each independently — no discount.

### Structure cluster (#14, #15, #17, #34, #35)

Bold overuse, inline-header lists, emojis, bullet-heavy formatting, and unnecessary numbered steps co-occur in formatted AI output (especially ChatGPT's bullet-heavy formatting).

**Scoring rule:** Count each independently but cap combined contribution at 10 points total.

### Conclusion cluster (#6, #24, #28)

Formulaic challenges, generic conclusions, and mirror conclusions appear in closing sections of AI text.

**Scoring rule:** When 2+ appear in the same closing section, count the highest at full points, others at 50%.

---

### Common co-occurrence pairs (informational)

These pairs frequently appear together but don't have special scoring rules:

| Pair | Why they co-occur |
|------|------------------|
| #1 + #3 | Inflated claims followed by -ing "analysis" |
| #7 + #25 | AI vocabulary inside "In today's world" openers |
| #8 + #7 | Copula avoidance uses AI vocabulary ("serves as a testament") |
| #26 + #1 | Dead metaphors used for significance inflation |
| #27 + #24 | "Meanwhile" transitions leading to generic conclusions |
| #29 + #10 | Uniform paragraphs with forced triplets |
| #32 + #4 | Rubber stamp qualifiers in promotional text |

---

*HumanInk Pattern Catalog — 35 patterns, cross-language detection, severity-weighted scoring.*
