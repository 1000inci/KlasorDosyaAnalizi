# Klasör Dosya Analizi (DAnaliz)

**DAnaliz**, Windows ortamında klasörler içindeki medya ve dosyaları analiz etmek için geliştirilmiş
grafik arayüzlü bir masaüstü uygulamasıdır.

Uygulama; video, görsel, ses dosyaları ve tekrar eden (duplicate) dosyalar hakkında
detaylı analiz yapar ve sonuçları Excel raporu olarak üretir.

> ⚡ Önerilen kullanım: Releases bölümündeki `DAnaliz.exe` dosyasını indirin (FFmpeg ve Python gerekmez).

---

## 🚀 Özellikler

- 📂 Klasör bazlı dosya analizi
- 🎬 Video analizi (codec, çözünürlük, süre)
- 🖼 Görsel ve 🎵 ses dosyası tespiti
- 🔁 Tekrarlanan dosya tespiti (SHA‑256 hash)
- ❌ Bozuk / hatalı medya dosyalarının tespiti
- 📊 Çok sayfalı Excel raporu oluşturma
- ✅ Gerçek zamanlı ilerleme çubuğu (% ve dosya sayısı)
- 🧵 Arka planda çalışma (arayüz donmaz)
- 🖥 Windows GUI (Tkinter)
- 📦 FFmpeg EXE içine gömülüdür (harici kurulum gerekmez)

---

## 📑 Oluşturulan Excel Sayfaları

Oluşturulan rapor, seçilen klasör içine kaydedilir ve aşağıdaki sayfaları içerebilir:

- **MedyaDosyalari**
  - Video / Görsel / Ses dosyaları (`Bozuk mu?` sütunu: EVET / HAYIR / BİLİNMİYOR)
- **TekrarlananDosyalar**
  - Aynı içeriğe sahip dosyalar (SHA‑256). Yalnız duplicate analizi işaretliyse üretilir.
- **SorunluDosyalar**
  - Bozuk olduğu **ölçülerek** saptanan medya dosyaları

Her sayfa yalnız içinde satır varsa oluşturulur; medya dışı dosyalar raporda
listelenmez, yalnız tarama sayısına girer.

---

## 🖥 Kullanıcı Arayüzü

- 🌙 Koyu tema
- 📈 Anlık ilerleme göstergesi
- 📊 “123 / 456 dosya analiz edildi — %27” gösterimi
- 🧠 Sadece istenen analizlerin çalıştırılması
- 📂 Tek tıkla rapor açma

---

## ▶ Kullanım (Script Olarak)

Python yüklü bir sistemde çalıştırmak için:

python DAnaliz.py

## ⚠ Önemli Not – FFmpeg Kullanımı

### 🔹 Script (.py) ile kullanım
Python script olarak çalıştırıldığında, **video analiz özellikleri** istiyorsanız (codec, çözünürlük, süre)
için **FFmpeg / ffprobe** gereklidir.

- FFmpeg bilgisayarda kurulu olmalı **veya**
- `ffprobe` / `ffprobe.exe` sistem PATH'inde bulunmalı **veya**
- `ffprobe.exe` script'in yanında olmalı (`ffmpeg/` alt klasöründe de aranır)

Aksi halde:
- Görsel / ses / duplicate analizi normal çalışır
- Video bilgileri (codec, çözünürlük, süre) boş kalır
- Bu videolar **bozuk sayılmaz ve yerlerinden oynatılmaz**; raporda
  `Bozuk mu?` sütununda **BİLİNMİYOR** yazar ve analiz sonunda kaç dosyanın
  ölçülemediği bildirilir

> ℹ️ "Ölçemedik" ile "bozuk" ayrı şeylerdir. Yalnız ffprobe'un okuyup
> reddettiği ve 0 baytlık dosyalar `SorunluDosyalar` klasörüne taşınır.

### 🔹 EXE (.exe) ile kullanım (ÖNERİLEN)
Release bölümünde sunulan **DAnaliz.exe**, FFmpeg’i **kendi içinde barındırır**.

✅ Harici FFmpeg kurulumu gerekmez  
✅ Python kurulumu gerekmez  
✅ Tek tıkla çalışır
