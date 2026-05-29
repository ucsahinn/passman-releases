# Yedekleme ve Geri Yükleme

PassMan yedeği encrypted payload, wrapped key, audit metadata ve integrity manifest içerir. Plaintext secret veya master password içermez.

## Önerilen İş Akışı

1. Güncelleme öncesi yedek alın.
2. Yedeği PassMan sunucu diski dışında saklayın.
3. Erişimi sınırlayın; yedek metadata açısından hassastır.
4. Geri yüklemeyi kontrollü ortamda test edin.

## Integrity

Import sırasında SHA-256 integrity manifest ve item count doğrulanır. Uyuşmazlık varsa import durdurulmalıdır.
