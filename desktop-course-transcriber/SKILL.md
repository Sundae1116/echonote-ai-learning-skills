---
name: desktop-course-transcriber
description: Design, build, or troubleshoot privacy-first desktop course transcription workflows that capture system audio, run local ASR, persist recoverable transcripts, and survive packaging. Use for Electron/Windows learning companions and local Whisper pipelines; not for bypassing DRM or extracting protected media.
---

# Desktop Course Transcriber

Build the smallest reliable pipeline that covers the user's actual playback surface. Confirm whether the course is a browser page, desktop app, or mini-program before selecting an extension or desktop companion.

## Architecture decisions

- Prefer a desktop companion when content cannot be reached through browser DOM or extension APIs.
- Treat captured PCM as ephemeral. Keep it in memory unless the user explicitly requests audio storage.
- Use a serialized transcription queue. On finish, stop capture, flush the final buffer, wait for queued work with a bounded timeout, then persist.
- Persist a draft after each accepted segment so an app restart can recover work.
- Separate capture, ASR, state, and rendering errors; give each a user-actionable recovery path.
- Never imply that ordinary capture can bypass DRM or operating-system restrictions.

## Quality gates

Judge the transcript on character/word error rate, domain-term accuracy, missing-segment rate, repetition rate, timestamp drift, latency, and long-run stability. A pipeline returning text is not sufficient if repeated hallucinations or lost tail segments make it unusable.

When packaging native ASR dependencies, test the packaged binary rather than only the development tree. Verify that the binding and runtime library versions match, and run a post-package model smoke test.

Read [references/reliability-checklist.md](references/reliability-checklist.md) when implementing capture lifecycle, recovery, or release validation.
