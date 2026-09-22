# DAnaliz – Media & File Analysis Tool

**DAnaliz** is a Windows desktop application designed to analyze folders containing media and general files.
It provides detailed insights into video, image, audio, and duplicate files, and generates comprehensive Excel reports.

> ⚡ Recommended usage: Download **DAnaliz.exe** from the **Releases** section  
> (No Python or FFmpeg installation required).

---

## 🚀 Features

- 📂 Folder-based file analysis
- 🎬 Video analysis (codec, resolution, duration)
- 🖼 Image and 🎵 audio file detection
- 🔁 Duplicate file detection using **SHA‑256 hash**
- ❌ Corrupted or broken media file detection
- 📊 Multi-sheet Excel report generation
- ✅ Real-time progress tracking (percentage + file count)
- 🧵 Background processing (UI never freezes)
- 🖥 Windows desktop GUI (Tkinter)
- 📦 FFmpeg embedded into the executable (no external dependency)

---

## 📑 Generated Excel Sheets

The generated Excel report is saved in the selected folder and may include:

- **MedyaDosyalari**
  - Video / Image / Audio files (`Bozuk mu?` column: EVET / HAYIR / BİLİNMİYOR)
- **TekrarlananDosyalar**
  - Duplicate files detected via SHA‑256. Only produced when duplicate analysis is enabled.
- **SorunluDosyalar**
  - Media files proven corrupted **by measurement**

A sheet is created only when it has rows. Non-media files are counted during
the scan but are not listed in the report.

---

## 🖥 User Interface Highlights

- 🌙 Dark mode interface
- 📈 Live progress indicator
- 📊 “456 / 1234 files analyzed — 36%”
- 🧠 Selective analysis (only required checks are executed)
- 📂 One-click Excel report opening

---

## ▶ Usage (Script Mode)

To run the project as a Python script:

```bash
python DAnaliz.py
```

---

## ⚠ Important – FFmpeg / ffprobe

### 🔹 Running as a script (.py)
Video analysis (codec, resolution, duration) requires **ffprobe**:

- FFmpeg installed on the machine, **or**
- `ffprobe` / `ffprobe.exe` available on the system `PATH`, **or**
- `ffprobe.exe` next to the script (also found under an `ffmpeg/` subfolder)

Without it:
- Image / audio / duplicate analysis still works
- Video fields stay empty
- Those videos are **not treated as corrupted and are not moved**; the report
  marks them **BİLİNMİYOR** and the completion dialog reports how many files
  could not be measured

> ℹ️ "Could not measure" is not the same as "corrupted". Only files ffprobe
> read and rejected — plus zero-byte files — are moved to `SorunluDosyalar`.

### 🔹 Running the EXE (recommended)
**DAnaliz.exe** from the Releases section bundles FFmpeg, so no external
FFmpeg or Python installation is needed.
