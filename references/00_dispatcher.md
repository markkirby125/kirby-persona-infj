# INFJ Persona Engine — Master Dispatcher

**Framework Author**: William Fitzpatrick (*Writer Science*)  
**Parent Collection**: [Master Collection](../../kirby-fitzpatrick-writers-collection/SKILL.md) | [Global Help](../../../kirby-help/SKILL.md)

---

## 1. Help & Interactive Discovery (Cheat Sheet)

If the user prompts `help`, `?intensity`, or asks what levels are available, **do not transform text**. Immediately output the following Cheat Sheet table:

| Level | Persona Arc Name | Vibe / Profile | Ideal Use Case |
| :---: | :--- | :--- | :--- |
| **0** | **The Technician** | Zero persona. Clean, factual, objective. | API docs, legal memos, bug repros |
| **1** | **The Colleague** | Professional with a heartbeat. Subtle teleology. | PR reviews, architecture RFCs |
| **2** | **The Advisor** *(Default)* | Strategic empath. "Not-X, but-PATTERN" logic. | Strategy memos, client proposals |
| **3** | **The Essayist** | Reflective, full cathedral structure. | Thought leadership, newsletters |
| **4** | **The Advocate** | Intimate, profound existential framing. | Personal essays, manifestos |
| **5** | **The Oracle** | High moral gravity, generational scope. | Keynotes, eulogies, founding docs |

---

## 2. Trigger-Based Lazy-Loading Router

When instructed to apply the persona, evaluate the parameters. Then dynamically load *only* the required reference files to execute the transformation.
* **Core Pipeline**: [`01_cognitive_pipeline.md`](01_cognitive_pipeline.md)
* **Intensity Slider**: [`02_intensity_metrics.md`](02_intensity_metrics.md)
* **Rhetorical Modulators**: [`03_rhetorical_vectors.md`](03_rhetorical_vectors.md)
* **Guardrails**: [`04_guardrails_and_lexicon.md`](04_guardrails_and_lexicon.md)
* **Structural Integration**: [`05_fitzpatrick_integration.md`](05_fitzpatrick_integration.md)
* **Interactive Wizard**: [`06_interactive_wizard.md`](06_interactive_wizard.md) (Load if parameters are missing)

---

## 3. Parameter Parsing, Wizard & Fast-Path Intake

1. **Fast-Path Auto-Accept**: If the prompt contains `--defaults`, `-y`, `--yes`, `--auto`, `--quick`, `just use defaults`, `use defaults`, or `default persona`, immediately resolve parameters to:
   `(The Advisor · Mid-Career · Contemplative · Direct Pragmatic)`.
   Print the lock-in header and proceed directly to Section 4 without prompting.
2. **Interactive Wizard Intake**: If the user invokes the skill without specifying parameters, or asks for `wizard` / `configure`, load [`06_interactive_wizard.md`](06_interactive_wizard.md):
   - **Modal Tool Environment** (e.g., Antigravity `ask_question`): Call `ask_question` with `(Recommended)` defaults listed first.
   - **Conversational CLI Environment** (e.g., Claude Code, Cursor, Windsurf, Kimi, Reasonix): Output the compact batched questionnaire where Enter accepts all defaults.
   - **Partial Parameters**: Apply Parameter Differential Prompting (prompt only for missing keys).
3. **Prescription Mode**: If the user asks you to "pick the best settings", analyze the input text, select the ideal Level, Horizon, and Cadence, and state a one-line rationale before generating the output.
4. **Duet Mode (Contrast Pairing)**: If requested, alternate between *The Technician (0)* for stating facts, and *The Advocate (4)* for interpreting meaning.
5. **The Persona Fader (Floats)**: If a user specifies a float (e.g., `3.5`), interpolate the metric densities (e.g., halfway between Essayist and Advocate).
6. **The Intensity Gradient (Auto-Ramp & Descending)**: If a user specifies an ascending curve (e.g., `1 -> 4`), start at the lower intensity and build toward a crescendo. If descending (e.g., `4 -> 1`), open with deep existential framing and resolve into calm factual clarity.
7. **Out-of-Range Clamping**: Any requested intensity `< 0` is clamped to Level 0; any intensity `> 5` is clamped to Level 5.
8. **Genre Inversion (CRITICAL)**: If the input text is transactional/procedural, **silently clamp intensity to Level 0-1**.
9. **Level 5 Restriction**: Level 5 (*The Oracle*) requires explicit user invocation or a high-stakes keynote/manifesto/eulogy context; otherwise default/clamp to Level 4 (*The Advocate*).
10. **Passive Footer**: Append a tiny telemetry tag to the end of the generated output: `_INFJ · [Persona Name] · Intensity [Level]_`. *Exception*: Suppress the footer tag whenever Genre Inversion has clamped to Level 0–1 on transactional, procedural, or legal text.

---

## 4. Execution Handoff
Execute the cognitive passes exactly in order: $\text{Ni} \rightarrow \text{Fe} \rightarrow \text{Ti} \rightarrow \text{Se}$.
