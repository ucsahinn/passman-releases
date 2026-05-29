# Paylaşım ve Offline Decrypter

PassMan seçili kayıt paylaşımını destekler. Kullanıcı tüm kasayı paylaşmak zorunda değildir; sadece seçilen kayıtlar şifreli paketlenir.

## İç Paylaşım

İç paylaşım, PassMan içinde kayıtlı kullanıcılar için kullanılır.

- Alıcı public key durumu kontrol edilir.
- Kasa anahtarı alıcı public key'i ile sarmalanır.
- Audit olayı yazılır.
- Alıcı yetkisi role ve vault access ile sınırlıdır.

## Dış Paylaşım

Dış paylaşım, PassMan kullanıcısı olmayan alıcılar için offline paket üretir.

Politika alanları:

- Son kullanma zamanı.
- Maksimum açma sayısı.
- Seçili kayıt listesi.
- Dosya kayıtları dahil edilecekse paket boyutu ve hassasiyet uyarısı.

## Offline Decrypter

`passman-share-decrypter.zip` içindeki HTML aracı tamamen tarayıcı içinde çalışır.

Güvenlik işaretleri:

- Local-only.
- Network bağlantısı gerekmez.
- Paket JSON, passphrase ve metadata tarayıcıda doğrulanır.
- Yanlış passphrase, değiştirilmiş metadata, expired paket ve kullanım limiti ayrı hata olarak gösterilir.
