# Public Host, HTTPS ve Sertifika

PassMan varsayılan olarak yerel HTTP portu ile başlar. Üretim kullanımında kontrollü DNS adı ve HTTPS önerilir.

## Host ve Port

Sunucu sistemi ekranında kullanılacak public host ve port tanımlanır.

Örnekler:

```text
passman.sirket.local
vault.example.com
```

Port varsayılanı:

```text
1903
```

## Sertifika

HTTPS etkinleştirilecekse PassMan'ın okuyabileceği sertifika paketi seçilmelidir. Operatör sertifika dosyasını sağlar; PassMan gereksiz sertifika kaynağı seçimi istemez.

Desteklenen paket tipi:

```text
PFX / P12
```

Güvenlik notları:

- Sertifika private key'i PassMan public repository'ye veya loglara konmamalıdır.
- Sertifika dosyası sunucuda sınırlı ACL ile saklanmalıdır.
- Kullanıcıların tarayıcı uyarısı görmemesi için host adı sertifika ile eşleşmelidir.

## Kontrol

1. Host adı DNS veya hosts dosyası üzerinden sunucuya çözülmeli.
2. Port firewall'da izinli olmalı.
3. Sertifika host adıyla eşleşmeli.
4. Tarayıcı `https://<HOST>:<PORT>` ile uyarısız açılmalıdır.
