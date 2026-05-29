# Windows Server Installation

## Requirements

- Windows Server or supported Windows desktop environment.
- Permission to run the MSI as Administrator.
- Inbound access for the selected TCP port.
- Backup or clean-install decision before production deployment.

## Install

1. Download the latest MSI: `PassMan-1.5.3-x64.msi`.
2. Run the MSI as Administrator.
3. The installer prepares the PassMan server files, bundled Node runtime, Prisma/SQLite runtime files, Windows service, firewall rule, and data/log directories.
4. Open PassMan from a browser:

```text
http://<SERVER_IP>:1903
```

## Default Paths

```text
C:\ProgramData\PassMan
C:\ProgramData\PassMan\logs
```

## Service

Service name:

```text
PassManServer
```

Display name:

```text
PassMan Server
```

## Verify

- `http://127.0.0.1:1903/api/profile` should respond on the server.
- Remote users can access `http://<SERVER_IP>:1903` when firewall and network rules allow it.
- Installer logs should be reviewed under `C:\ProgramData\PassMan\logs`.
