# Sharing and Offline Decrypter

PassMan supports selected-record sharing. Users do not need to share an entire vault; only selected records are encrypted into a package.

## Internal Sharing

Internal sharing is for users already registered in PassMan.

- Recipient public key state is checked.
- The vault key is wrapped for the recipient public key.
- An audit event is written.
- Recipient access is limited by role and vault access.

## External Sharing

External sharing creates an offline package for recipients outside the PassMan server.

Policy fields:

- Expiry time.
- Maximum open count.
- Selected record list.
- File-record inclusion with package-size and sensitivity warnings.

## Offline Decrypter

The HTML tool inside `passman-share-decrypter.zip` runs fully in the browser.

Trust indicators:

- Local-only.
- No network connection required.
- Package JSON, passphrase, and metadata are verified in the browser.
- Wrong passphrase, tampered metadata, expired package, and exhausted usage limit are separate errors.
