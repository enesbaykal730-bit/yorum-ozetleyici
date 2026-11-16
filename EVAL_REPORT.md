# Eval Raporu — Akıllı Yorum Özetleyici (`v-vize`)

Bu rapor, `evals/cases.yaml` içerisinde yer alan 20 senaryonun yerel test ve doğrulama sonuçlarını özetler.

## Özet Sonuçlar
- **Toplam Senaryo:** 20
- **Başarılı (Geçen):** 20 (%100)
- **Başarısız (Kalan):** 0

## Grup Bazlı Dağılım
| Grup | Senaryo Sayısı | Geçen | Kalan | Açıklama |
| :--- | :---: | :---: | :---: | :--- |
| `normal` | 8 | 8 | 0 | Farklı ürün kategorileri ve `tr`/`en` dil ayarları şemaya tam uyumlu çıktı üretti. |
| `edge` | 5 | 5 | 0 | Tek yorum, emoji içeren kısa yorumlar, çelişkili ifadeler ve madde sınırları doğru işlendi. |
| `error` | 3 | 3 | 0 | Boş yorum listesi, eksik ürün adı ve tanımsız operasyon isteklerine `422` hata kodu döndü. |
| `attack` | 4 | 4 | 0 | Prompt injection, fiyat uydurma zorlaması, XSS ve SSRF girişimleri başarıyla engellendi. |

## Güvenlik ve Sözleşme Doğrulamaları
- `GET /health` uç noktası < 50 ms sürede `{"status": "ok"}` yanıtı vermektedir.
- Geçersiz `X-Platform-Signature` veya 300 saniyeden eski `X-Platform-Timestamp` başlıkları `401` ile reddedilmektedir.
- Kişisel veri (PII) ve yorum içerikleri sunucu loglarına yazılmamaktadır.
