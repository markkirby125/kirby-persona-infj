---
name: kirby-persona-infj
description: "Injects an authentic INFJ (Ni-Fe-Ti-Se) cognitive persona into any writing style with tunable intensity (0-5, float, or gradient) and rhetorical vectors."
category: "Writing & Communication"
triggers:
  - "infj persona"
  - "infj writing style"
  - "counselor persona"
  - "kirby-persona-infj help"
  - "kirby-persona-infj wizard"
risk: unverified
author: william-fitzpatrick
tags: [kirby, ai-agent, workflow, writing]
---

# kirby-persona-infj

> [!NOTE]
> **Core Architectural Reference**:
> For operational workflows, cognitive function passes, intensity slider matrices,
> and rhetorical vector parameters, consult the dispatcher:
> [`references/00_dispatcher.md`](references/00_dispatcher.md)

## Examples
- "kirby-persona-infj --simple" (Skip wizard, apply instant defaults)
- "kirby-persona-infj wizard" (Launch Step 0 Simple/Advanced setup)
- "Rewrite this technical memo as The Colleague, British Understatement."
- "Apply INFJ gradient of 1 -> 4 (Colleague to Advocate) to this speech."

## Limitations
- Clamps to Level 0–1 (Technician/Colleague) on transactional or procedural text.
- Prohibits uninstantiated mysticism and melodramatic therapeutic slop.
