# 🚀 n8n + yt-dlp Automation Setup

A powerful automation system using **n8n**, **yt-dlp**, and **FFmpeg** to download, process, and send videos automatically.

---

## 📌 Features

* 🎥 YouTube video download
* 🎵 Audio extraction (MP3)
* 🤖 Telegram auto-send
* 📁 File management (list, delete, search)
* 💾 Storage monitoring
* ⚙️ Execute Command support

---

## 🧠 Requirements

* n8n (Self Hosted / Railway)
* FFmpeg
* Node.js
* yt-dlp
* Telegram Bot Token

---

## ⚙️ Installation (Railway Worker)

```bash
/bin/sh -c "apk add --no-cache ffmpeg curl python3 py3-pip nodejs npm && curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp && chmod a+rx /usr/local/bin/yt-dlp && n8n worker"
```

---

## 🎥 yt-dlp Commands

### ▶️ Download Video

```bash
yt-dlp --js-runtimes node -f best -o "/home/node/video.mp4" "URL"
```

### 🎵 Extract Audio (MP3)

```bash
yt-dlp --js-runtimes node -x --audio-format mp3 "URL"
```

### 📋 List Available Formats

```bash
yt-dlp --js-runtimes node -F "URL"
```

### 📄 Get Video Info

```bash
yt-dlp --js-runtimes node --dump-json "URL"
```

---

## 📁 File Management Commands

### 📂 List Files

```bash
ls -lh /home/node/
```

### 🔍 Search Videos

```bash
find /home/node/ -name "*.mp4"
```

### 🗑️ Delete File

```bash
rm /home/node/video.mp4
```

---

## 💾 Storage Commands

### 📊 Check Disk Space

```bash
df -h
```

### 📁 Folder Usage

```bash
du -sh /home/node/
```

### 🎥 Video Sizes

```bash
du -sh /home/node/*.mp4
```

---

## 🔧 Debug Commands

```bash
yt-dlp --version
ffmpeg -version
python3 --version
node -v
```

---

## 📤 Telegram Workflow

### 🔄 Flow

YouTube Link
↓
Execute Command (yt-dlp)
↓
Read Binary File
↓
Telegram Send Video

---

### ⚠️ Important Settings

* Use **Binary Property = data**
* Do NOT use local URL
* Do NOT execute `.mp4` file

---

## ❌ Common Mistakes

❌ Running video file:

```bash
/home/node/video.mp4
```

❌ Using localhost URL in Telegram

---

## 💡 Tips

* Use short videos (safe for Railway)
* Prefer audio extraction (faster)
* Avoid large downloads

---

## 🚀 Future Improvements

* Telegram auto-download bot
* Web UI downloader
* Cloud storage integration
* Auto cleanup system

---

## 👨‍💻 Author

Built with ❤️ using n8n + yt-dlp
