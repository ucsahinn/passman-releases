# Backups and Restore

PassMan backups contain encrypted payloads, wrapped keys, audit metadata, and an integrity manifest. They do not contain plaintext secrets or master passwords.

## Recommended Workflow

1. Export a backup before updates.
2. Store the backup outside the PassMan server disk.
3. Restrict access; backup metadata is sensitive.
4. Test restore in a controlled environment.

## Integrity

Import verifies the SHA-256 integrity manifest and item counts. If the values do not match, stop the import.
