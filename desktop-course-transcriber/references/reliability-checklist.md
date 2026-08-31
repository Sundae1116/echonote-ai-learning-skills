# Reliability checklist

## Capture lifecycle

- Source selection works without a prefilled course title.
- Start resets buffers only for a genuinely new session.
- Pause stops accumulation without destroying state.
- Finish flushes the final PCM buffer and waits for queued transcription.
- Delete cancels pending work so results cannot leak into the next course.
- Restart restores transcript, highlights, title, and elapsed time.
- The displayed timer freezes while paused and resumes from accumulated active time.

## ASR quality

- Normalize sample rate and channel count consistently.
- Detect pathological consecutive repetition without deleting legitimate emphasis.
- Keep timestamps monotonic after asynchronous results.
- Preserve raw recognized text until a cleaning rule is validated on a representative set.

## Release

- Lock native dependency versions.
- Verify packaged native libraries are unpacked when required.
- Run syntax, workflow, migration, DOM, and packaged-runtime smoke tests.
- Test first-model download, offline reuse, proxy behavior, mirror fallback, and retry messaging.
- Verify custom data locations after restart and upgrade; active capture must block location changes.
