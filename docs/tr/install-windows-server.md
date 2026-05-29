# Windows Server Kurulumu

## Gereksinimler

- Windows Server veya desteklenen Windows masaüstü ortamı.
- Administrator yetkisiyle MSI çalıştırma izni.
- Kullanılacak TCP portu için inbound erişim.
- Kurulumdan önce alınmış yedek veya temiz kurulum kararı.

## Kurulum

1. En güncel MSI dosyasını indirin: `PassMan-1.5.3-x64.msi`.
2. MSI'ı administrator olarak çalıştırın.
3. Kurulum PassMan Server dosyalarını, bundled Node runtime'ını, Prisma/SQLite runtime dosyalarını, Windows servisini, firewall kuralını ve log/data dizinlerini hazırlar.
4. Kurulum sonrası tarayıcıdan açın:

```text
http://<SERVER_IP>:1903
```

## Varsayılan Dizinler

```text
C:\ProgramData\PassMan
C:\ProgramData\PassMan\logs
```

## Servis

Windows servis adı:

```text
PassManServer
```

Görünen ad:

```text
PassMan Server
```

## Kontrol

- `http://127.0.0.1:1903/api/profile` sunucu üzerinde cevap vermeli.
- Uzak kullanıcılar firewall ve ağ izinleri uygunsa `http://<SERVER_IP>:1903` ile erişebilmelidir.
- Kurulum logları `C:\ProgramData\PassMan\logs` altında incelenmelidir.
