# 🚀 n8n + yt-dlp Automation Setup

Ye project ek powerful automation system hai jisme:

- n8n workflow automation
- yt-dlp video downloader
- FFmpeg support
- Telegram integration

use karke YouTube videos ko download karke automatically process/send kiya ja sakta hai.

---

## ⚙️ Features

✅ YouTube video download  
✅ Audio extraction (MP3)  
✅ Telegram auto-send  
✅ File management (list, delete, storage check)  
✅ Execute Command support  

---

## 🧠 Requirements

- n8n (Self Hosted / Railway)
- FFmpeg installed
- Node.js installed
- yt-dlp installed
- Telegram Bot Token

---

## 📦 Installation (Worker Start Command)

```bash
/bin/sh -c "apk add --no-cache ffmpeg curl python3 py3-pip nodejs npm && curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp && chmod a+rx /usr/local/bin/yt-dlp && n8n worker"
