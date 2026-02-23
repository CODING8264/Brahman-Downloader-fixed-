# ब्राह्मण Media Downloader

<div align="center">

![Logo](https://img.shields.io/badge/ब्राह्मण-Media%20Downloader-ff6a00?style=for-the-badge&logo=android&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Android-green?style=for-the-badge&logo=android)
![Powered By](https://img.shields.io/badge/Powered%20By-yt--dlp-red?style=for-the-badge)
![Sites](https://img.shields.io/badge/Sites-1000%2B-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**A powerful media downloader app inspired by YTDLnis**  
**Built with Node.js + Capacitor + yt-dlp**

</div>

---

## ✨ Features

- ⬇ **Download from 1000+ sites** — YouTube, Instagram, Twitter, Facebook & more
- 🎬 **Video downloads** — Best, 4K, 1440p, 1080p, 720p, 480p, 360p
- 🎵 **Audio downloads** — MP3, M4A, OPUS, FLAC, WAV, AAC
- 📋 **Batch downloads** — Multiple links at once
- 🖼 **Embed Thumbnail** — Auto embed into file
- 🏷 **Embed Metadata** — Title, artist, album info
- 💬 **Embed Subtitles** — Auto download & embed
- 📚 **Chapters support** — Embed video chapters
- 💰 **SponsorBlock** — Skip sponsor segments
- 🎛 **Format selector** — See all available formats
- 📜 **Download history** — Full log of all downloads
- 📁 **File browser** — Browse downloaded files
- 🔄 **Queue manager** — View and cancel active downloads
- ✏ **Filename template** — Custom filename patterns
- 🌐 **Standalone APK** — Connects to Termux backend

---

## 🚀 How It Works

```
┌─────────────────┐         ┌──────────────────────┐
│  Android APK    │ ──────► │  Termux Node.js      │
│  (This App)     │  WiFi   │  Server (index.js)   │
│                 │ ◄────── │                      │
└─────────────────┘         └──────────────────────┘
                                       │
                                       ▼
                             ┌──────────────────────┐
                             │   yt-dlp             │
                             │  Downloads file to   │
                             │  /Download/Brahman/  │
                             └──────────────────────┘
```

---

## 📦 Installation

### Step 1 — Setup Termux Backend

Install Termux from F-Droid (NOT Play Store):
👉 https://f-droid.org/packages/com.termux/

```bash
# Update packages
pkg update && pkg upgrade

# Install required tools
pkg install nodejs python

# Give storage permission
termux-setup-storage

# Install yt-dlp
pip install yt-dlp --break-system-packages

# Setup backend
mkdir ~/backend && cd ~/backend
npm init -y
npm install express

# Start server
node index.js
```

---

### Step 2 — Install the APK

1. Go to **[Releases](../../releases)** tab
2. Download `BrahmanDownloader.apk`
3. Install on your Android phone
4. Allow installation from unknown sources if prompted

---

### Step 3 — Connect App to Server

1. Open the app
2. Find your IP in Termux:
```bash
ip addr show wlan0
# Look for inet like 192.168.x.x
```
3. Enter `192.168.x.x:3000` in the app
4. Tap **Connect to Server**

> ⚠️ App and Termux must be on **same WiFi**

---

## 🔧 Build APK Yourself

1. **Fork this repository**
2. Go to **Actions → Build APK → Run workflow**
3. Wait **10-15 minutes**
4. Go to **Actions → Latest run → Artifacts**
5. Download **BrahmanDownloader-APK**

---

## 📁 Repository Structure

```
brahman-downloader/
├── .github/
│   └── workflows/
│       └── build.yml          ← GitHub Actions APK builder
├── www/
│   └── index.html             ← Standalone app UI
├── package.json               ← Capacitor dependencies
├── capacitor.config.json      ← Android config
└── README.md                  ← This file
```

---

## 💾 Download Location

```
/storage/emulated/0/Download/Brahman/
├── Video/    ← MP4, WEBM, MKV
└── Audio/    ← MP3, M4A, OPUS, FLAC
```

---

## 🛠 Tech Stack

| Component | Technology |
|-----------|-----------|
| Backend | Node.js + Express |
| Downloader | yt-dlp |
| Frontend | HTML + CSS + JS |
| APK Wrapper | Capacitor 5 |
| Build CI | GitHub Actions |
| Runtime | Termux (Android) |

---

## ⚠️ Notes

- Keep Termux running with `node ~/backend/index.js`
- Both must be on **same WiFi network**
- Grant storage permission: `termux-setup-storage`
- Install Termux from **F-Droid** not Play Store

---

<div align="center">

Made with ❤️ | Powered by yt-dlp | 1000+ sites supported

</div>
