# Active Directory and PassMan DC Agent Service

PassMan DC Agent Service runs on the domain side and safely synchronizes directory objects into PassMan.

## Service Identity

```text
Service name: PassManDCAgent
Display name: PassMan DC Agent Service
```

## Install

Download `passman-ad-agent.ps1` from the release assets and run it from an Administrator PowerShell:

```powershell
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -InstallService -PassManUrl "<PASSMAN_URL>" -AgentId "<AGENT_ID>" -AgentToken "<AGENT_TOKEN>"
```

The AD bind password is requested locally in the terminal. It is not sent to PassMan and is not written to logs.

## Useful Commands

```powershell
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -Status
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -TailLog
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -RepairService
```

## UI

After sync, PassMan displays OU, group, and user objects as a tree. Operators manage login scope and credential import scope with separate checkbox selections.

## Troubleshooting

- Prefer `DOMAIN\username` or `username@domain.local` for bind usernames.
- Verify `<PASSMAN_URL>` from the agent machine.
- Agent logs should redact token and password values.
