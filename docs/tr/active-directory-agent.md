# Active Directory ve PassMan DC Agent Service

PassMan DC Agent Service, domain tarafında çalışan ve PassMan'a directory objelerini güvenli şekilde aktaran servis bileşenidir.

## Servis Kimliği

```text
Service name: PassManDCAgent
Display name: PassMan DC Agent Service
```

## Kurulum

Release asset'inden `passman-ad-agent.ps1` indirilir ve administrator PowerShell ile çalıştırılır:

```powershell
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -InstallService -PassManUrl "<PASSMAN_URL>" -AgentId "<AGENT_ID>" -AgentToken "<AGENT_TOKEN>"
```

AD bind password terminalde yerel olarak istenir. Bu parola PassMan'a gönderilmez ve loglara yazılmaz.

## Yararlı Komutlar

```powershell
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -Status
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -TailLog
powershell -ExecutionPolicy Bypass -File .\passman-ad-agent.ps1 -RepairService
```

## UI Deneyimi

Senkron sonrası PassMan, OU, group ve user objelerini ağaç yapısında gösterir. Operatör checkbox'larla login kapsamını ve credential import kapsamını ayrı ayrı yönetir.

## Sorun Giderme

- Bind username için `DOMAIN\username` veya `username@domain.local` formatı tercih edin.
- PassMan URL erişimini agent makinesinden doğrulayın.
- Agent loglarında token ve password değerleri redacted görünmelidir.
