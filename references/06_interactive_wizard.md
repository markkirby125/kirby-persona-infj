# Interactive Wizard Protocol & Fast-Path Engine

**Parent Collection**: [Master Collection](../../kirby-fitzpatrick-writers-collection/SKILL.md) | [Dispatcher](00_dispatcher.md)

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

## 2. Fast-Path Auto-Accept

### Trigger Detection
Evaluate the user prompt before starting any questionnaire:
* **Flag triggers**: `--defaults`, `-y`, `--yes`, `--auto`, `--quick`
* **Natural language**: `just use defaults`, `use defaults`, `default persona`
* **Prescription shorthand**: `surprise me`, `pick for me`, `auto settings` (resolves to Prescription Mode)

### Auto-Accept Resolution
Immediately resolve to `(The Advisor · Mid-Career · Contemplative · Direct Pragmatic)`. Print the lock-in line:
> `_INFJ Persona Locked: The Advisor (L2) · Mid-Career · Contemplative · Direct Pragmatic. (Re-run with 'wizard' or 'configure' to customize)._`

Then proceed straight to the cognitive pipeline. Do not prompt any questions.

---

## 3. Multi-Environment Execution Tiers

### Tier A: Native Modal Tool (`ask_question`)
If the environment provides an interactive UI modal tool (e.g., Antigravity `ask_question` or IDE GUI pickers):
* Call `ask_question` with the 4 questions in order (or batched if supported).
* Always place the default option first, prefixed with `(Recommended)`.
* When the user clicks or presses Enter on `(Recommended)`, the default is confirmed instantly.
* Example modal schema:
  - **Question 1**: "Which Persona Arc intensity would you like to apply?"
    - `(Recommended) The Advisor (Level 2) — Strategic empath, 'Not-X, but-PATTERN' logic`
    - `The Colleague (Level 1) — Professional with a heartbeat, subtle teleology`
    - `The Essayist (Level 3) — Reflective thought leadership, Cathedral structure`
    - `The Advocate (Level 4) — Intimate, profound existential framing`
    - `The Technician (Level 0) — Zero persona, crisp linear facts`
    - `The Oracle (Level 5) — High moral gravity, generational scope`
    - `Auto-pick — Prescription mode (analyze text and pick for me)`
  - **Question 2**: "Which Generational Horizon fits the vantage point?"
    - `(Recommended) Mid-Career / Steward (35–50s) — Second-order effects, sustainable architecture`
    - `Youth / Idealist (20s) — Future-forward momentum, tech-native idioms`
    - `Elder / Sage (60s+) — Historical parallax, multi-generational cycles, aphoristic calm`
  - **Question 3**: "Which Rhetorical Tradition Cadence?"
    - `(Recommended) Direct Pragmatic — Transparent honesty, optimistic resolve, accessible warmth`
    - `Litotes / Restrained — British understatement, dry irony, courteous reticence`
    - `High-Context Harmonic — Relational equilibrium, deference over dogmatism, collective harmony`
    - `Communal Oratorical — Proverbial architecture, call-and-response rhythm, gravitas`
    - `Lyrical / Atmospheric — Celtic/Irish poetic rhythm, mythic undertones`
  - **Question 4**: "Which Energy & Temperament Register?"
    - `(Recommended) Contemplative — Spacious, questions left to breathe (Adagio)`
    - `Pastoral / Mentor — Warm, supportive guidance, growth metaphors (Andante)`
    - `Forensic / Architectural — Cool, sharp, evidence-driven scrutiny (Moderato)`
    - `Prophetic — Soaring, urgent, high moral stakes (Crescendo)`

---

### Tier B: Conversational / Terminal CLI Fallback
If no modal tool is present (e.g., Claude Code, Cursor chat, Windsurf terminal, Kimi, Reasonix), output a single compact batched questionnaire:

```text
🧠 INFJ Persona Wizard — Press Enter (blank reply) to accept all recommended defaults, or pick your numbers:

1. Persona Arc:    [1] The Advisor (Recommended)  [2] The Colleague  [3] The Essayist  [4] The Advocate  [5] The Technician  [6] The Oracle  [7] Auto-pick
2. Horizon:        [1] Mid-Career / Steward (Recommended)  [2] Youth / Idealist  [3] Elder / Sage
3. Cadence:        [1] Direct Pragmatic (Recommended)  [2] Litotes  [3] High-Context  [4] Communal  [5] Lyrical
4. Energy:         [1] Contemplative (Recommended)  [2] Pastoral  [3] Forensic  [4] Prophetic

Reply with your choices (e.g., "1=3, 4=2"), or hit Enter / type "default" to accept all.
```

* **Parsing Rules**:
  - Blank reply or `default` / `d` / `y` $\rightarrow$ Accepts all 4 recommended defaults.
  - Comma-separated or space-separated numbers map directly.
  - Partial inputs only prompt for the missing fields (**Parameter Differential Prompting**).

---

## 4. Parameter Differential Prompting
If the user specifies *some* parameters in their initial prompt (e.g., `"Rewrite this memo using kirby-persona-infj as The Advocate"`):
1. Extract the specified parameter (`intensity = 4 / The Advocate`).
2. Skip Question 1.
3. Only prompt for the remaining missing parameters (Horizon, Energy, Cadence), with defaults pre-selected.

---

## 5. Lock-In & Transition
Once parameters are resolved (via fast-path, modal tool, or conversational CLI):
1. Print the lock-in header:
   > `_INFJ Persona Locked: [Persona Arc] · [Horizon] · [Energy] · [Cadence]_`
2. Load [`01_cognitive_pipeline.md`](01_cognitive_pipeline.md) and [`05_fitzpatrick_integration.md`](05_fitzpatrick_integration.md).
3. Execute the $\text{Ni} \rightarrow \text{Fe} \rightarrow \text{Ti} \rightarrow \text{Se}$ pipeline.
