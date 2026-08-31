---
name: local-data-portability
description: Design, implement, or audit local-first application backup, restore, import/export, storage-location changes, and upgrade-safe data migration. Use when a desktop app must move all historical and future data to a user-selected folder without loss, duplication, split-brain state, or silent rollback.
---

# Local Data Portability

Treat changing a data location as a migration transaction. The feature is complete only when historical data, future writes, secrets, caches, backups, and restart behavior all agree on one canonical location.

## Migration contract

1. Resolve and validate the source and destination before writing. Reject the current folder, nested source/destination paths, protected paths, and ambiguous non-empty targets.
2. Block migration while capture, transcription, import, backup, or another write-heavy workflow is active.
3. Create a staging directory at the destination. Copy only the documented managed dataset.
4. Verify the staged tree by relative path, byte size, and cryptographic hash for critical files.
5. Persist a small location pointer in a stable default application directory using atomic replace.
6. Switch the running process to the new canonical location and perform read-after-write checks.
7. Remove managed source items only after successful verification and switch-over. Preserve unrelated files.
8. On any failure, keep the original location authoritative, remove incomplete staging data, and show an actionable error.

## Managed dataset

Inventory data explicitly. A learning companion commonly includes the primary database, drafts, transcript segments, review history, settings, backups, encrypted API credentials, model cache, migration metadata, and diagnostic logs. Do not assume that moving one JSON or database file moves the product state.

## Upgrade and recovery

- Keep the location pointer backward-compatible and independent from the movable dataset.
- Make schema migrations idempotent and record their version.
- Detect an interrupted migration on startup and choose one authoritative copy using committed metadata, never modification time alone.
- Provide backup/export before destructive repair and keep imports non-destructive until validation succeeds.
- Display the active path and provide an "open data folder" action so users can verify where their data lives.

Read [references/migration-checklist.md](references/migration-checklist.md) before implementing, testing, or releasing a storage-location change.
