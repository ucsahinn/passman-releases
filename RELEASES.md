# PassMan Release Notes

Latest public release: **PassMan Enterprise Vault Console 1.5.3**

Release page: https://github.com/ucsahinn/passman-releases/releases/tag/v1.5.3

## PassMan 1.5.3

### Console 1.5.3

- Supersedes 1.5.2 for Windows MSI upgrades.
- Hardened major MSI upgrades from older PassMan Server installs where `RemoveExistingProducts` could run before the elevated execute sequence and fail with Windows Installer error `1730` / `1603`.
- Keeps the 1.5.x enterprise console scope: dynamic theme engine, executive overview, actionable security posture, selected-record sharing, 15-minute RAM fast unlock, file-backed shares, RBAC, audit, diagnostics, and Update Center polish.
- Keeps the self-hosted Windows MSI server model with Prisma/SQLite persistence and browser-side vault unlock.
- SQLCipher remains deferred hardening; sensitive payloads are encrypted before SQLite persistence.

### Chromium Extension 3.1.8

- Active-site badge counts show how many matching PassMan records are available for the current site.
- Autofill, save-login, and update-login prompts remain available after pairing and unlock.
- Browser notifications avoid plaintext usernames, passwords, or secret values.

### Offline Share Decrypter 1.2.0

- Opens selected-record external share packages locally in the browser.
- Supports file-backed share records.
- Enforces package expiry and usage limits.
- Shows distinct error states for invalid JSON, wrong passphrase, tampered metadata, expired packages, and exhausted usage limits.

### PassMan DC Agent Service 1.0.10

- Installs the Windows service as `PassManDCAgent` with display name `PassMan DC Agent Service`.
- Supports install, repair, status, tail-log, and online-requirement modes.
- Captures the AD bind password locally and does not send it to PassMan.
- Redacts agent ids, tokens, passwords, and secret-like values from agent/service logs.

### Verification Summary

- Lint, TypeScript, Vitest, Next standalone build, extension package, share decrypter package, DC Agent package, UI smoke checks, Windows MSI packaging, Authenticode signing, update manifest issue/verify, and source-focused secret scans passed before publication.
- Local MSI upgrade testing can still require an elevated Windows Installer context on the target machine.

<details>
<summary>PassMan 1.5.2</summary>

### Console 1.5.2

- Hardened the self-update path around job progress, target version tracking, stale install reconciliation, helper logs, verbose Windows Installer logs, and local signer messaging.
- Build output tracing was cleaned so local `.data`, `dist`, tests, signing artifacts, and source folders are not traced into standalone route metadata.

### Extension 3.1.8

- No package behavior change from 1.5.1.

### Decrypter 1.2.0

- No package behavior change from 1.5.1.

### DC Agent 1.0.10

- No package behavior change from 1.5.1.

</details>

<details>
<summary>PassMan 1.5.1</summary>

### Console 1.5.1

- Active Directory provider selection renders synced OU, group, and user objects as a searchable tree.
- Login scope and credential import selections are separated with clear checkbox states, branch-level credential selection, and count chips for large domains.
- Empty, waiting, and no-match states on the AD provider surface clarify whether the blocker is first sync, filtering, or missing users.

### DC Agent 1.0.10

- Fixed service wrapper install failures caused by overwriting `PassManDCAgentService.exe` while an existing service was still running.
- Added service repair, status, tail-log, online requirement, wrapper compile logging, and redacted logs.

### Extension 3.1.8

- Active-site match badge counts, autofill prompts, save/update login prompts, and notifications remain available.

### Decrypter 1.2.0

- Offline selected-record decryption, file package support, expiry, usage limits, and local-only messaging remain available.

</details>

<details>
<summary>PassMan 1.5.0</summary>

- Consolidated the PassMan Enterprise Vault Console UI pass.
- Added dynamic light/dark theme tokens across shell, cards, charts, CTAs, focus states, and gradient surfaces.
- Added selected-record sharing including file records.
- Added 15-minute browser-process RAM fast unlock.
- Refined component version visibility so the main MSI and browser extension are the actionable Update Center cards.
- Added extension autofill/save/update prompts and browser notifications without exposing secret values.

</details>

## Older History

Earlier 1.0.x through 1.4.x builds established the self-hosted MSI baseline, offline licensing, selected-secret sharing, browser extension management, update manifests, file vault work, RBAC, audit hardening, and enterprise UI polish. Public downloads for those builds are retired; use the latest stable release.
