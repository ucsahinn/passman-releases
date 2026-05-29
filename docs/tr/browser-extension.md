# Chromium Extension

PassMan Chromium Extension, eşleşmiş cihazlarda kullanıcı aksiyonuyla autofill, save login, update login ve siteye ait kayıt sayısı badge'i sağlar.

## Kurulum Yolları

- Enterprise policy ile yönetilen dağıtım.
- ZIP fallback paketi ile manuel/operasyonel kurulum.

Chrome normal web sayfasından sessiz extension kurulumu yapmaz. Otomatik dağıtım için enterprise policy, Chrome Web Store veya imzalı CRX update akışı gerekir.

## Eşleştirme

1. Extension popup'ta PassMan server origin girilir.
2. Kullanıcı adı, cihaz adı ve extension PIN'i tanımlanır.
3. Extension kısa süreli eşleştirme kodu üretir.
4. PassMan Extension ekranında cihaz onaylanır.
5. Kasa anahtarları extension public key'i için sarmalanır.

## Güvenlik

- Extension private key ve pair token, Chromium profilinde PIN ile sarmalanır.
- Persistent storage plaintext secret içermez.
- Autofill snapshot'ları encrypted payload ve extension-wrapped key içerir.
- Plaintext sadece kullanıcı aksiyonu sonrası extension oturumunda çözülür.
- Cihaz kaybolursa PassMan panelinden revoke edilmelidir.
