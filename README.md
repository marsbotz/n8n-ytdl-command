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
yt-dlp --js-runtimes node -o "/root/.n8n-files/video.mp4" "URL"
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

## 🏷️ Metadata Extraction Commands

### 📄 Get Title

```bash
yt-dlp --js-runtimes node --get-title "URL"
```

### 👤 Get Uploader / Channel Name

```bash
yt-dlp --js-runtimes node --get-uploader "URL"
```

### ⏱️ Get Duration

```bash
yt-dlp --js-runtimes node --get-duration "URL"
```

### 🆔 Get Video ID

```bash
yt-dlp --js-runtimes node --get-id "URL"
```

### 🖼️ Get Thumbnail URL

```bash
yt-dlp --js-runtimes node --get-thumbnail "URL"
```

### 📅 Get Upload Date

```bash
yt-dlp --js-runtimes node --get-upload-date "URL"
```

### 🔥 Get Full JSON Data

```bash
yt-dlp --js-runtimes node --dump-json "URL"
```
###
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
🎬 🔰 BASIC COMMANDS
▶️ Video info check
ffmpeg -i input.mp4
🔄 Format convert
ffmpeg -i input.mkv output.mp4
🎥 Extract audio
ffmpeg -i input.mp4 -q:a 0 -map a output.mp3
🖼️ Extract images
ffmpeg -i input.mp4 frame_%04d.png
✂️ CUT / TRIM COMMANDS
⏱️ First 45 sec
ffmpeg -i input.mp4 -t 45 output.mp4
🎯 Specific time se cut
ffmpeg -ss 00:01:00 -i input.mp4 -t 45 output.mp4
⚡ Fast cut (no re-encode)
ffmpeg -ss 00:01:00 -i input.mp4 -t 45 -c copy output.mp4
🔊 AUDIO COMMANDS
🎵 Audio remove
ffmpeg -i input.mp4 -an output.mp4
🔊 Volume increase
ffmpeg -i input.mp4 -filter:a "volume=2.0" output.mp4
🎧 Audio convert
ffmpeg -i input.wav output.mp3
🎞️ VIDEO EDIT COMMANDS
📉 Compress video
ffmpeg -i input.mp4 -vcodec libx264 -crf 28 output.mp4
📏 Resize video
ffmpeg -i input.mp4 -vf scale=1280:720 output.mp4
🔄 Change FPS
ffmpeg -i input.mp4 -r 30 output.mp4
🌀 Rotate video
ffmpeg -i input.mp4 -vf "transpose=1" output.mp4
🧩 ADVANCED COMMANDS
🎬 Merge video + audio
ffmpeg -i video.mp4 -i audio.mp3 -c:v copy -c:a aac output.mp4
🧱 Concatenate videos
ffmpeg -f concat -safe 0 -i list.txt -c copy output.mp4
🎥 Create GIF
ffmpeg -i input.mp4 -t 5 output.gif
🧊 Add watermark
ffmpeg -i input.mp4 -i logo.png -filter_complex "overlay=10:10" output.mp4
🔥 STREAM / PIPE COMMANDS
📡 Pipe input/output
ffmpeg -i pipe:0 -f mp4 pipe:1
🌐 Stream URL
ffmpeg -i "https://example.com/video.mp4" output.mp4
⚙️ CODEC COMMANDS
🎬 H.264 encode
ffmpeg -i input.mp4 -c:v libx264 output.mp4
🎥 H.265 encode
ffmpeg -i input.mp4 -c:v libx265 output.mp4
🔊 AAC audio
ffmpeg -i input.mp4 -c:a aac output.mp4
⚡ SPEED CONTROL
⏩ Fast video
ffmpeg -i input.mp4 -filter:v "setpts=0.5*PTS" output.mp4
🐢 Slow motion
ffmpeg -i input.mp4 -filter:v "setpts=2.0*PTS" output.mp4
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

