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

## 2025-03-25 — Kod temizliği

- Kullanılmayan `--mono` CSS değişkeni silindi
- Gereksiz `[data-theme="dark"] .seg button.on` override kaldırıldı
- `handleCSVFile` referanslı ölü `<input>` elementi kaldırıldı
- İşlevsel değişiklik yok — import/export ve storage mekanizması korundu

## Önceki değişiklikler (commit geçmişinden)

- CSV header'ları Türkçeleştirildi (`camTipi` → `Cam`, `kasa` → `Kasa`, `kayis` → `Kayış`)
- Liste görünümündeki alan erişimleri güncellendi (`w.kasa` → `w['Kasa']`, `w.camTipi` → `w['Cam']`)
- Modal referans ve CSV handling refactor edildi
- `data.csv` sonundaki newline düzeltildi
