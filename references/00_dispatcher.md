# INFJ Persona Engine — Master Dispatcher

**Framework Author**: William Fitzpatrick (*Writer Science*)  
**Parent Collection**: [Master Collection](../../kirby-fitzpatrick-writers-collection/SKILL.md) | [Global Help](../../../kirby-help/SKILL.md)

---

## 1. Trigger-Based Lazy-Loading Router

This skill manages a massive 432-state parameter space (6 intensities × 3 horizons × 6 cadences × 4 registers). **Do not load all reference files at once.**

When instructed to apply the INFJ persona, read the user's requested parameters. Then, dynamically read *only* the required reference files to execute the transformation.

* **Core Pipeline (Always Load)**: [`01_cognitive_pipeline.md`](01_cognitive_pipeline.md)
* **Intensity Slider (Always Load)**: [`02_intensity_metrics.md`](02_intensity_metrics.md)
* **Rhetorical Modulators (Load if specified)**: [`03_rhetorical_vectors.md`](03_rhetorical_vectors.md)
* **Guardrails (Always Load)**: [`04_guardrails_and_lexicon.md`](04_guardrails_and_lexicon.md)
* **Structural Integration (Always Load)**: [`05_fitzpatrick_integration.md`](05_fitzpatrick_integration.md)

---

## 2. Parameter Parsing & Precedence Rules

1. **Genre Inversion (CRITICAL)**: If the input text is transactional, procedural, legal, or purely functional (e.g., bash scripts, API tables, refund policies), **silently clamp intensity to Level 0 or Level 1**. High-intensity INFJ prose on procedural text creates parody.
2. **Precedence**: Guardrails > Explicit User Params > Defaults.
3. **Defaults**: If parameters are omitted, default to:
   - *Intensity*: Level 2 (Attuned Analyst)
   - *Horizon*: Mid-Career / Steward
   - *Cadence*: None (Neutral)
   - *Register*: Contemplative

---

## 3. Execution Handoff
Once parameters are parsed and validated, load the necessary reference files from the list above and execute the cognitive passes exactly in order: $\text{Ni} \rightarrow \text{Fe} \rightarrow \text{Ti} \rightarrow \text{Se}$.
