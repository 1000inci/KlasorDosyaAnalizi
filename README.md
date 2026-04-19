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
  - Video / Görsel / Ses dosyaları
- **MedyaDisiDosyalar** (isteğe bağlı)
  - Medya dışı dosyalar
- **TekrarlananDosyalar**
  - Aynı içeriğe sahip dosyalar (SHA‑256)
- **SorunluDosyalar**
  - Bozuk medya dosyaları

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
- `ffprobe.exe` sistem PATH'inde bulunmalıdır

Aksi halde:
- Görsel / ses / duplicate analizi çalışır
- Video bilgileri boş veya kısıtlı olabilir

### 🔹 EXE (.exe) ile kullanım (ÖNERİLEN)
Release bölümünde sunulan **DAnaliz.exe**, FFmpeg’i **kendi içinde barındırır**.

✅ Harici FFmpeg kurulumu gerekmez  
✅ Python kurulumu gerekmez  
✅ Tek tıkla çalışır
