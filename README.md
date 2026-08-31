# EchoNote AI Learning Skills

Reusable Codex skills distilled from building **EchoNote 3.0**, a privacy-first Windows learning companion that turns desktop course audio into transcripts, structured knowledge, translations, and spaced review while keeping local data portable.

## Skills

| Skill | Use it for |
|---|---|
| `desktop-course-transcriber` | Local system-audio capture, ASR lifecycle, recovery, transcript quality, and packaged-runtime validation |
| `course-knowledge-distiller` | Faithful summaries, long-course chunking, study translation, prompt contracts, and output evaluation |
| `spaced-review-designer` | Complete recall cards, learner answer comparison, spaced scheduling, and visible learning outcomes |
| `local-data-portability` | Safe backup, import/export, storage-location changes, atomic migration, rollback, and upgrade compatibility |

## Install

Copy an individual skill folder into your Codex skills directory, or install from this repository using the Codex skill installer.

```text
~/.codex/skills/<skill-name>/SKILL.md
```

Each skill is intentionally independent. Install only the capability your workflow needs.

## Design principles

- Use deterministic code for state, permissions, scheduling, and destructive actions.
- Use models for speech recognition and semantic transformation.
- Keep humans in control of source correction, highlights, mastery judgments, and cloud transmission.
- Define quality with measurable dimensions rather than “looks good.”
- Test the packaged artifact, not only the development environment.
- Treat a storage-location change as a verified migration transaction, not a settings-field update.

## Privacy and scope

These skills contain instructions and evaluation rubrics only. They do not contain course audio, transcripts, API keys, model files, or the EchoNote application source.

Do not use them to bypass DRM, platform restrictions, copyright controls, or authorization boundaries.

## License

MIT
