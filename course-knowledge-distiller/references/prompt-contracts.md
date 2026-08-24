# Prompt contracts

## Summary

System constraints:

- Use only supplied course content.
- Separate the speaker's claims, supporting evidence, and suggested actions.
- Do not silently repair factual claims with outside knowledge.

Input sections:

1. Course title and context.
2. User-marked highlights, explicitly higher priority.
3. Timestamped transcript.

Output contract:

- One-sentence thesis.
- Core framework and reasoning chain.
- Key evidence and caveats.
- Action checklist.
- Memorable formulations.
- Recall questions with complete, self-contained answers.

## Translation

- Preserve proper names, numbers, claims, and paragraph order.
- Make style configurable: faithful, natural, or concise for memorization.
- In bilingual mode, keep paragraph alignment explicit.
- Never replace or mutate the source transcript.
