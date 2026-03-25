# Changelog

## Proje Durumu

- **Yapı:** Tek sayfa web uygulaması — `index.html` + `data.csv`
- **Koleksiyon:** 18 Casio saat (Vintage, G-Shock, Edifice, Duro serileri)
- **Veri:** CSV'den yükleniyor. Önce `window.storage` kontrol edilir, yoksa `data.csv` okunur
- **CSV Import:** Kullanıcı kendi CSV'sini yükleyebilir, `window.storage`'a kaydedilir ve default'u override eder
- **CSV Export:** Mevcut koleksiyonu CSV olarak indirir
- **Temalar:** light / dark (default) / retro
- **Görünümler:** grid (default) / list
- **Filtreleme:** Seri bazlı tab filtre + metin araması + sıralama (tarih, model, seri, mekanizma)
- **Modal:** Tıklanan saatin detay sayfası — fotoğraf, özellik badge'leri, teknik spec grid
- **CSV Sütunları:** `modelAdi, referansNo, seri, mekanizma, Kadran, Cam, Kasa, Kayış, tarih, ozellikler, fotografUrl`

## 2026-03-25 — data.csv detaylandırması

- Tüm saatlerin özellik (ozellikler) alanları genişletildi (Saatlik Sinyal, Pil ömrü, Geri Sayım Zamanlayıcı vb.)
- Bio-Based malzeme bilgisi eklendi (F-91WPC, GW-BX5600, DW-6900RGM kasa/kayış)
- Mekanizma isimleri Türkçeleştirildi (Analog Chronograph → Analog Kronograf)
- GST-B1000D mekanizması düzeltildi (Analog-Digital Solar → Analog Solar)
- Pil ömrü bilgisi eklendi (2, 3, 5, 7, 10 Yıl Pil)
- DW-6900RGM: Japonya Yapımı, Flaş Alarm gibi detaylar eklendi
- GM-B2100D: Tough Solar ve Dünya Saati eklendi
- A1000DN: Dünya Saati kaldırıldı (hatalıydı)

## 2026-03-25 — Kod temizliği

- Kullanılmayan `--mono` CSS değişkeni silindi
- Gereksiz `[data-theme="dark"] .seg button.on` override kaldırıldı
- `handleCSVFile` referanslı ölü `<input>` elementi kaldırıldı
- İşlevsel değişiklik yok — import/export ve storage mekanizması korundu

## Önceki değişiklikler (commit geçmişinden)

- CSV header'ları Türkçeleştirildi (`camTipi` → `Cam`, `kasa` → `Kasa`, `kayis` → `Kayış`)
- Liste görünümündeki alan erişimleri güncellendi (`w.kasa` → `w['Kasa']`, `w.camTipi` → `w['Cam']`)
- Modal referans ve CSV handling refactor edildi
- `data.csv` sonundaki newline düzeltildi
