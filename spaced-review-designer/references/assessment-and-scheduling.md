# Assessment and scheduling

## Answer comparison

Use lexical coverage only as a cheap, explainable baseline. It cannot reliably judge paraphrases, reversed causality, or logically incorrect answers containing the right terms.

For higher quality, combine:

1. Deterministic checks for required names, numbers, and negations.
2. Embedding similarity for paraphrase recall.
3. Rubric-based LLM judging for correctness, completeness, and error type.
4. Confidence and supporting evidence shown to the learner.

Calibrate against human-labeled correct, partially correct, synonymous, and confidently wrong answers.

## Scheduling

Keep scheduling deterministic and inspectable. A simple baseline can map:

- forgot: short interval and lapse increment;
- unclear: moderate interval growth;
- mastered: longer multiplicative growth.

Store the decision and next date. When the algorithm changes, migrate state explicitly rather than silently resetting learning history.
