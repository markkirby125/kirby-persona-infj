# kirby-persona-infj

*This skill is part of the [Kirby Skills Writers Collection](https://github.com/markkirby125/kirby-fitzpatrick-writers-collection) and the broader [Kirby Skills Ecosystem](https://github.com/markkirby125/kirby-skills-collection).*

A psycholinguistically grounded AI agent skill that injects an authentic **INFJ** (*Introverted Intuition → Extraverted Feeling → Introverted Thinking → Extraverted Sensing*) cognitive persona into any writing style—from high-stakes architecture RFCs and technical documentation to strategic memos, personal essays, and keynote speeches.

---

## Why Most "Persona Prompts" Fail (And How This Fixes It)

Standard LLM persona prompts like *"write as an INFJ"* almost always trigger one of two toxic AI failure modes:
1. **The Therapist Slop Trap**: Breathless pseudo-empathy, over-validation, intrusive patronizing phrases (*"I see you and hold space for your journey"*), and emotional sighs at the end of every paragraph.
2. **The Fortune-Cookie Mystic Trap**: Portentous vagueness, cosmic clichés (*"as the universe aligns"*), and ungrounded aphorisms that collapse under logical inspection.

`kirby-persona-infj` solves this by treating the INFJ archetype not as an aesthetic "vibe," but as a **deterministic four-layer cognitive pipeline** executing on top of William Fitzpatrick's empirical writing science (*Writer Science*):

```text
[Draft Input]
     │
     ▼
┌────────────────────────────────────────────────────────┐
│ 1. Dominant Ni Pass: Vision & Teleological Framing     │
│    - Reframe from destination backward.               │
│    - Deploy the "Not-X, but-PATTERN" structural move.   │
│    - Build the Cathedral structure (Keystone ➔ Bell).  │
└──────────────────────────┬─────────────────────────────┘
                           ▼
┌────────────────────────────────────────────────────────┐
│ 2. Auxiliary Fe Pass: Relational Attunement            │
│    - Validate human motivations before redirection.    │
│    - Conversational cadence & epistemic "we".          │
└──────────────────────────┬─────────────────────────────┘
                           ▼
┌────────────────────────────────────────────────────────┐
│ 3. Tertiary Ti Pass: Analytical Precision              │
│    - Resolve modal hedges into falsifiable claims.     │
│    - Surgical definitional precision & fluff removal.  │
└──────────────────────────┬─────────────────────────────┘
                           ▼
┌────────────────────────────────────────────────────────┐
│ 4. Inferior Se Pass: Terrestrial Grounding             │
│    - Rationed, tactile physical anchors at pivots.     │
│    - Ground the abstraction in concrete reality.       │
└──────────────────────────┬─────────────────────────────┘
                           ▼
               [Calibrated INFJ Output]
```

---

## Key Features

### 1. The Persona Arc (Plain-English Intensity)
No need to memorize abstract numbers. Pick who you want speaking:
* **The Technician (Level 0)**: Zero persona. Linear, crisp, objective facts for API docs, bug repros, and legal notices.
* **The Colleague (Level 1)**: Professional with a heartbeat. Subtle teleological framing for PR reviews and architecture RFCs.
* **The Advisor (Level 2 - Default)**: The strategic empath. Deploys *"Not-X, but-PATTERN"* reasoning for strategy memos and engineering proposals.
* **The Essayist (Level 3)**: Full Cathedral structure with rhythmic periodic sentences for thought leadership and essays.
* **The Advocate (Level 4)**: Intimate, profound existential framing and recurring symbolic anchors for manifestos and personal essays.
* **The Oracle (Level 5 - Restricted)**: Generational scope and high moral gravity for keynotes, eulogies, and founding documents.

### 2. Multi-Dimensional Rhetorical Modulators
Dial in age horizons and rhetorical traditions without resorting to caricatures:
* **Generational Horizons**: 
  - *Youth / Idealist (20s)*: Future-forward momentum, tech-native idioms, em-dash drive.
  - *Mid-Career / Steward (35–50s)*: Consequence-focused, second-order effects, organizational empathy.
  - *Elder / Sage (60s+)*: Multi-generational parallax, historical depth, aphoristic distillation.
* **Rhetorical Cadences**:
  - *High-Context Harmonic*: Relational equilibrium, deference over dogmatism, collective harmony.
  - *Litotes / Restrained*: British understatement, dry irony, courteous reticence (*"not entirely without merit"*).
  - *Communal Oratorical*: Proverbial architecture, call-and-response rhythm, communal gravitas.
  - *Direct Pragmatic*: Transparent emotional honesty, optimistic resolve, accessible warmth.
  - *Lyrical / Atmospheric*: Celtic/Irish poetic rhythm, mythic undertones, atmospheric beauty.

### 3. Advanced Tuning Modes
* **The Intensity Gradient (Auto-Ramp)**: Declare a curve like `1 -> 4`. The document opens as *The Colleague* (calm facts) and builds momentum until it crescendos as *The Advocate*.
* **The Persona Fader (Floats)**: Ask for `3.5` to interpolate beat density directly between *The Essayist* and *The Advocate*.
* **Duet Mode**: Alternate between *The Technician* stating raw system facts and *The Advocate* interpreting their human meaning.
* **Prescription Mode**: Simply say *"pick the best settings"*, and the skill analyzes your draft, justifies a recommendation, and applies it.

### 4. Built-in Slop & Genre Defense
* **Genre Inversion Guardrail**: If applied to purely procedural text (a bash script or refund policy), the skill automatically clamps to Level 0–1 to prevent absurdity.
* **The Ti Inversion Gate**: Every abstract claim must instantly identify a concrete real-world mechanism, or it is deleted.
* **Banned Lexicon Filters**: Hard-blocks pop-psychology buzzwords (*holding space*, *lean into*, *energetic alignment*, *the universe*).

---

## Getting Started

### 1. Installation via The Magic Prompt
Copy and paste this into any AI coding app (Cursor, Windsurf, Claude Code, Grok, Kimi, Reasonix):

```markdown
@agent Install the kirby-persona-infj skill from: https://github.com/markkirby125/kirby-persona-infj
1. Read `SKILL.md` and `references/` from the repository.
2. Place into your environment's skills/rules directory preserving the dispatcher structure.
3. Confirm when installation is complete.
```

### 2. Manual Installation
Clone this repository directly into your agent's skills directory:
```bash
git clone https://github.com/markkirby125/kirby-persona-infj.git ~/.gemini/config/skills/kirby-persona-infj
```
*(Also compatible with `~/.cursor/skills`, `~/.codeium/windsurf/skills`, `~/.grok/skills`, `~/.kimi-code/skills`, and `~/.reasonix/skills`).*

---

## Usage Examples

### 1. Quick Discovery (Cheat Sheet)
```text
kirby-persona-infj help
```
*Outputs the complete 6-row Persona Arc table with use-case guidance.*

### 2. Strategic Engineering Proposal
```text
"Rewrite this proposal memo using kirby-persona-infj as The Advisor, Mid-Career horizon, Litotes cadence."
```

### 3. Keynote Speech with an Auto-Ramp Gradient
```text
"Apply kirby-persona-infj with a gradient of 1 -> 4 (Colleague to Advocate) in Lyrical register to this speech draft."
```

### 4. Let the Skill Decide
```text
"Rewrite this launch announcement using kirby-persona-infj prescription mode."
```

---

## Architecture & Directory Layout

```text
kirby-persona-infj/
├── SKILL.md                          # Hollow shell dispatcher (≤ 200 tokens)
├── README.md                         # Project documentation & manual
├── .gitignore                        # Standard exclusions
└── references/
    ├── 00_dispatcher.md              # Master lazy-loading router & parameter parser
    ├── 01_cognitive_pipeline.md      # Strict Ni ➔ Fe ➔ Ti ➔ Se I/O contracts
    ├── 02_intensity_metrics.md       # Measurable thresholds for The Persona Arc
    ├── 03_rhetorical_vectors.md      # Generational horizons & rhetorical cadences
    ├── 04_guardrails_and_lexicon.md  # Ti Inversion gate & banned slop lexicons
    └── 05_fitzpatrick_integration.md # Topic-Comment, Locomotive & Cathedral mappings
```

---

## Attribution & Provenance
* **Ecosystem**: Kirby Agent Skills Monorepo
* **Methodology**: William Fitzpatrick (*Writer Science*) & Carl Jung / MBTI Cognitive Linguistics
* **Author**: markkirby125
* **License**: MIT
