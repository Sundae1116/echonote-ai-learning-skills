# Migration checklist

## Preconditions

- Resolve canonical absolute paths and compare case-insensitively on Windows.
- Reject destination paths inside the source and source paths inside the destination.
- Require enough free space for the dataset plus staging overhead.
- Decide and document whether a non-empty destination is supported; default to rejecting it.
- Suspend autosave and reject migration during recording or transcription.

## Transaction

- Create a unique staging folder under the selected destination.
- Copy the complete managed-data manifest without following unsafe links.
- Verify counts, sizes, and hashes for the primary store, secrets, and pointer metadata.
- Flush writes before atomically committing the location pointer.
- Reopen the primary store from the new location and perform a read/write probe.
- Clean only known managed items from the old location after commit.

## Failure injection

Test cancellation or failure during copy, verification, pointer commit, process switch, and cleanup. After every injected failure, restarting the app must expose one complete authoritative dataset and no mixed-location writes.

## Compatibility matrix

Cover default-to-custom, custom-to-custom, custom-to-default, empty and populated datasets, Unicode and long paths, insufficient space, permission denial, antivirus/file locks, restart after migration, upgrade with a custom location, backup/restore at a custom location, and rollback to an older application version.

## Product acceptance

- The UI explains that both historical and future data move.
- Progress cannot be mistaken for completion.
- Success displays the final canonical path.
- "Open data folder," backup, restore, full export, and full import all operate on that same path.
- No user content is deleted until the new copy is verified and active.
