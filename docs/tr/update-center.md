# Güncelleme Merkezi

PassMan Update Center, ana Windows MSI paketini ve Chromium extension paketini yönetir. Offline Share Decrypter ve DC Agent Service, MSI ile yenilenen destek bileşenleri olarak release notlarında izlenir.

## Güvenli Güncelleme Modeli

PassMan şu kontrolleri yapar:

- İmzalı update manifest doğrulaması.
- Paket URL ve dosya adı kontrolü.
- SHA-256 hash doğrulaması.
- MSI Authenticode signer thumbprint kontrolü.
- Paket boyutu ve metadata kontrolü.

Global CA zinciri PassMan'ın kendi update güveni için zorunlu değildir; imzalı manifest local signer thumbprint'ini pin'lediğinde PassMan paketi kabul edebilir. Windows SmartScreen itibarı için CA-backed veya trusted signing hâlâ önerilir.

## Release Assets

Güncel public release şu asset'leri içerir:

- `PassMan-1.5.3-x64.msi`
- `passman-update.json`
- `passman-chromium-extension.zip`
- `passman-share-decrypter.zip`
- `passman-ad-agent.ps1`

## Operasyon Önerileri

- Güncelleme öncesi yedek alın.
- MSI imzasını ve manifest durumunu kontrol edin.
- Güncelleme sonrası servis durumunu ve versiyonu doğrulayın.
- Hata durumunda installer ve PassMan loglarını birlikte inceleyin.
