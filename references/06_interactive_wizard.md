# Interactive Wizard Protocol & Fast-Path Engine

**Parent Collection**: [Master Collection](../../kirby-fitzpatrick-writers-collection/SKILL.md) | [Dispatcher](00_dispatcher.md) | [Use-Case Recipes](../docs/use_case_recipes.md)

This protocol governs interactive parameter intake when a user invokes `kirby-persona-infj` without specifying explicit parameters.

---

## 1. Canonical Default Tuple

When parameters are omitted, the engine defaults to the calibrated equilibrium:

| Parameter | Key | Canonical Default | Options |
|---|---|---|---|
| **Q1: Persona Arc** | `intensity` | **(Recommended) The Advisor (Level 2)** | The Technician (0), The Colleague (1), The Advisor (2), The Essayist (3), The Advocate (4), The Oracle (5), Auto-pick (Prescription) |
| **Q2: Generational Horizon** | `horizon` | **(Recommended) Mid-Career / Steward (35–50s)** | Youth / Idealist (20s), Mid-Career / Steward (35–50s), Elder / Sage (60s+) |
| **Q3: Rhetorical Cadence** | `cadence` | **(Recommended) Direct Pragmatic** | Direct Pragmatic, Litotes / Restrained, High-Context Harmonic, Communal Oratorical, Lyrical / Atmospheric |
| **Q4: Energy Register** | `register` | **(Recommended) Contemplative** | Contemplative, Pastoral / Mentor, Forensic / Architectural, Prophetic |

---

## 2. Fast-Path Auto-Accept (Bypassing the Wizard)

### Trigger Detection
Evaluate the user prompt before starting any questionnaire:
* **Simple flags**: `--simple`, `-s`, `--defaults`, `-y`, `--yes`, `--auto`, `--quick`
* **Natural language**: `simple infj`, `just use defaults`, `use defaults`, `default persona`
* **Prescription shorthand**: `surprise me`, `pick for me`, `auto settings` (resolves to Prescription Mode)

### Auto-Accept Resolution
Immediately resolve to `(The Advisor · Mid-Career · Contemplative · Direct Pragmatic)`. Print the lock-in line:
> `_INFJ Persona Locked: The Advisor (L2) · Mid-Career · Contemplative · Direct Pragmatic. (Re-run with '--advanced' to customize)._`

Then proceed straight to the cognitive pipeline. Do not prompt any questions.

---

## 3. Curated 1-Click Archetype Presets

When users want a fast, high-impact configuration without answering 4 questions:

1. **Strategic Work / Proposals** (`--preset work`):
   * *Tuple*: The Advisor (L2) · Mid-Career · Forensic / Architectural · Direct Pragmatic
   * *Ideal for*: Strategy memos, client proposals, architectural specs, project escalations.
2. **Essay / Thought Leadership** (`--preset essay`):
   * *Tuple*: The Essayist (L3) · Mid-Career · Contemplative · Lyrical / Atmospheric
   * *Ideal for*: Editorial essays, newsletters, articles, founder reflections.
3. **Team & Code Reviews** (`--preset team`):
   * *Tuple*: The Colleague (L1) · Mid-Career · Pastoral / Mentor · Direct Pragmatic
   * *Ideal for*: Peer PR reviews, design doc critiques, team announcements, post-mortems.

*(For detailed real-world scenarios, consult [`docs/use_case_recipes.md`](../docs/use_case_recipes.md)).*

---

## 4. Multi-Environment Execution Tiers (The Step 0 Fork)

### Tier A: Native Modal Tool (`ask_question`)
If the environment provides an interactive UI modal tool (e.g., Antigravity `ask_question` or IDE GUI pickers):

1. **Step 0: Gating Fork Modal**:
   * **Question 0**: "How would you like to set up the INFJ Persona?"
     - `(Recommended) Simple Mode — Apply balanced defaults immediately & start writing`
     - `1-Click Presets — Pick a curated use-case archetype (Work / Essay / Team)`
     - `Advanced Mode — Open full 4-step customization wizard (Intensity, Horizon, Cadence, Energy)`
   * **Resolution**:
     - *If Simple Mode selected*: Resolve canonical defaults and proceed straight to execution (zero further questions).
     - *If 1-Click Presets selected*: Prompt a 1-question selector for Work, Essay, or Team.
     - *If Advanced Mode selected*: Render Questions 1 through 4 sequentially.

2. **Advanced Mode Sequence (Questions 1–4)**:
   - **Question 1 (Persona Arc)**:
     - `(Recommended) The Advisor (Level 2) — Strategic empath, 'Not-X, but-PATTERN' logic`
     - `The Colleague (Level 1) — Professional with a heartbeat, subtle teleology`
     - `The Essayist (Level 3) — Reflective thought leadership, Cathedral structure`
     - `The Advocate (Level 4) — Intimate, profound existential framing`
     - `The Technician (Level 0) — Zero persona, crisp linear facts`
     - `The Oracle (Level 5) — High moral gravity, generational scope`
     - `Auto-pick — Prescription mode (analyze text and pick for me)`
   - **Question 2 (Generational Horizon)**:
     - `(Recommended) Mid-Career / Steward (35–50s) — Second-order effects, sustainability`
     - `Youth / Idealist (20s) — Future-forward momentum, tech-native idioms`
     - `Elder / Sage (60s+) — Historical parallax, multi-generational cycles`
   - **Question 3 (Rhetorical Cadence)**:
     - `(Recommended) Direct Pragmatic — Transparent honesty, accessible warmth`
     - `Litotes / Restrained — British understatement, dry irony, courteous reticence`
     - `High-Context Harmonic — Relational equilibrium, collective harmony`
     - `Communal Oratorical — Proverbial architecture, call-and-response rhythm`
     - `Lyrical / Atmospheric — Celtic/Irish poetic rhythm, mythic undertones`
   - **Question 4 (Energy Register)**:
     - `(Recommended) Contemplative — Spacious, questions left to breathe (Adagio)`
     - `Pastoral / Mentor — Warm, supportive guidance, growth metaphors (Andante)`
     - `Forensic / Architectural — Cool, sharp, evidence-driven scrutiny (Moderato)`
     - `Prophetic — Soaring, urgent, high moral stakes (Crescendo)`

---

### Tier B: Conversational / Terminal CLI Fallback
If no modal tool is present (e.g., Claude Code, Cursor chat, Windsurf terminal, Kimi, Reasonix), output a single compact batched questionnaire:

```text
🧠 INFJ Persona Setup — Choose a mode (Press Enter for Simple Mode):

[1] Simple Mode (Recommended) — Apply balanced defaults and write immediately
[2] 1-Click Presets — Pick Work, Essay, or Team presets
[3] Advanced Wizard — Customize all 4 parameters (Intensity, Horizon, Cadence, Energy)

Reply '1' or press Enter to proceed with Simple Mode, or '3' for Advanced:
```

* **Parsing Rules**:
  - Blank reply or `1` / `simple` / `default` / `d` / `y` $\rightarrow$ Accepts Simple Mode immediately (zero further prompts).
  - If `3` or `advanced` is replied $\rightarrow$ Displays Questions 1–4.
  - Partial inputs apply **Parameter Differential Prompting** (prompts only for missing keys).

---

## 5. Lock-In & Transition
Once parameters are resolved (via fast-path, modal tool, or conversational CLI):
1. Print the lock-in header:
   > `_INFJ Persona Locked: [Persona Arc] · [Horizon] · [Cadence] · [Energy] · Tip: Run with '--advanced' to customize._`
2. Load [`01_cognitive_pipeline.md`](01_cognitive_pipeline.md) and [`05_fitzpatrick_integration.md`](05_fitzpatrick_integration.md).
3. Execute the $\text{Ni} \rightarrow \text{Fe} \rightarrow \text{Ti} \rightarrow \text{Se}$ pipeline.
