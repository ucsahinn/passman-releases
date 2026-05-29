# Chromium Extension

PassMan Chromium Extension provides user-action autofill, save-login, update-login, and active-site record-count badges on paired devices.

## Installation Modes

- Enterprise policy deployment.
- ZIP fallback package for manual or emergency installation.

Chrome does not allow a normal web page to silently install an extension. Automatic deployment requires enterprise policy, Chrome Web Store, or a signed CRX update flow.

## Pairing

1. Enter the PassMan server origin in the extension popup.
2. Set username, device name, and extension PIN.
3. The extension generates a short-lived pairing code.
4. Approve the device in the PassMan Extension screen.
5. Vault keys are wrapped for the extension public key.

## Security

- Extension private key and pair token are wrapped with the extension PIN in the Chromium profile.
- Persistent storage does not contain plaintext secrets.
- Autofill snapshots contain encrypted payloads and extension-wrapped keys.
- Plaintext is decrypted only in the extension session after user action.
- Revoke lost or untrusted devices from the PassMan panel.
