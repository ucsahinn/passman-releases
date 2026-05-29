# Update Center

PassMan Update Center manages the main Windows MSI package and the Chromium extension package. Offline Share Decrypter and DC Agent Service are support components refreshed by the MSI and tracked in release notes.

## Secure Update Model

PassMan verifies:

- Signed update manifest.
- Package URL and file name.
- SHA-256 hash.
- MSI Authenticode signer thumbprint.
- File size and metadata.

A global CA chain is not required for PassMan-managed update trust when the signed manifest pins the local release signer thumbprint. CA-backed or trusted signing is still recommended for Windows SmartScreen reputation.

## Release Assets

The current public release contains:

- `PassMan-1.5.3-x64.msi`
- `passman-update.json`
- `passman-chromium-extension.zip`
- `passman-share-decrypter.zip`
- `passman-ad-agent.ps1`

## Operations

- Export a backup before updating.
- Check the MSI signature and manifest status.
- Verify service status and version after the update.
- Review installer and PassMan logs together when updates fail.
