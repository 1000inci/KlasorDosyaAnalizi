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
  - Video / Image / Audio files
- **MedyaDisiDosyalar** (optional)
  - Non-media files
- **TekrarlananDosyalar**
  - Duplicate files detected via SHA‑256
- **SorunluDosyalar**
  - Corrupted or problematic media files

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
