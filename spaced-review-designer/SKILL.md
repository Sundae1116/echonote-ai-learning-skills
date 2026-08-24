---
name: spaced-review-designer
description: Design active-recall and spaced-review experiences from structured learning content, including complete cards, optional learner answers, explainable comparison, scheduling, and progress dashboards. Use for learning products that must show what was retained rather than only store notes.
---

# Spaced Review Designer

Make the learner attempt retrieval before revealing the reference answer. Build cards from curated summaries or explicit highlights, not arbitrary slices of noisy transcripts.

## Card construction

- A question must be answerable from one self-contained knowledge block.
- Preserve multi-line answers as one block; do not extract a single matching sentence.
- Keep source course, section, and evidence location so the learner can verify context.
- Deduplicate semantically equivalent cards and preserve progress across content migrations when possible.

## Review interaction

- Learner answer is optional, but skipping must be recorded distinctly from an incorrect answer.
- Show the complete reference answer before mastery rating.
- Explain comparison using covered concepts, missing concepts, and uncertainty. Do not present lexical overlap as semantic correctness.
- Persist attempts, ratings, intervals, lapses, next due date, and source version.

## Outcomes

Expose daily activity, total attempts, mastered cards, weak concepts, per-course coverage, answer history, and next scheduled work. A stored event without a visible learning outcome is incomplete product value.

Read [references/assessment-and-scheduling.md](references/assessment-and-scheduling.md) for scoring and interval guidance.
