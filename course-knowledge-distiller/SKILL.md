---
name: course-knowledge-distiller
description: Turn noisy course transcripts and user highlights into faithful structured summaries, study translations, and review-ready knowledge blocks. Use when designing prompts, chunking long lessons, defining output quality, or keeping AI derivatives traceable to edited source material.
---

# Course Knowledge Distiller

Treat transcription, user intent, and generated derivatives as separate layers. Preserve the full transcript, prioritize explicit user highlights, and never overwrite source material with a model output.

## Distillation workflow

1. Clean only demonstrated ASR artifacts; retain uncertain wording for human correction.
2. Partition the prompt into course metadata, user highlights, timestamped transcript, constraints, and output contract.
3. For long input, summarize chunks into evidence-bearing notes, then synthesize globally. Do not concatenate independent summaries without resolving duplication and contradictions.
4. Require a structure suited to the downstream task: thesis, framework, reasoning chain, evidence, actions, memorable formulations, and complete recall Q&A.
5. Mark summaries and translations stale when their source transcript changes.

## Definition of good

Evaluate fidelity, key-point recall, structure compliance, compression, usefulness, terminology consistency, number/name preservation, and evidence traceability. Treat invented facts as a hard failure even when prose is polished.

Read [references/prompt-contracts.md](references/prompt-contracts.md) for summary and translation contracts. Read [references/evaluation-rubric.md](references/evaluation-rubric.md) when comparing prompts or models.
