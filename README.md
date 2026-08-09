# 🦉 Owl Learner — German YouTube Bot v10

Automated pipeline to generate, render, and upload engaging **German learning YouTube Shorts** using AI-generated scripts, voice synthesis, and FFmpeg video processing.

---
## 🚀 Features
* 🎯 **Fully Automated Workflow**

  * Generates German vocabulary content using AI (Groq API)
  * Creates audio narration (multi-engine fallback system)
  * Downloads background visuals
  * Renders high-quality vertical videos
  * Uploads directly to YouTube (scheduled)
* 🧠 **Smart Content Generation**

  * Difficulty-based word selection (Beginner → Advanced)
  * Avoids repeating previously used words
  * Generates:

    * German word + meaning
    * Example sentences
    * Hook & outro scripts
    * Dynamic comment engagement prompts

* 🔊 **Advanced Text-to-Speech**

  * Priority order:

    1. `pyttsx3` (offline)
    2. `edge-tts`
    3. `gTTS`
  * Auto normalization + resampling (44100 Hz) → **perfect sync**

* 🎬 **Professional Video Rendering**

  * 1080x1920 vertical format
  * 7 structured segments:

    1. Hook
    2. Intro
    3. German Word
    4. Translation
    5. Example Sentence
    6. Tagline
    7. Comment Prompt (NEW 🔥)
  * Smooth transitions (xfade + audio crossfade)
  * Dynamic text overlays
  * Background music + logo support

* 💬 **Engagement Optimization**

  * Dynamic question prompts based on example sentence
  * Encourages comments & retention
  * Adds CTA in video + description

---

## 📦 Installation

Install required dependencies:

```bash
pip install pyttsx3 edge-tts gtts google-api-python-client \
            google-auth-httplib2 google-auth-oauthlib requests
```

---

## ⚙️ Configuration

Edit the following variables at the top of the script:

```python
GROQ_API_KEY = "your_api_key_here"

CHANNEL_LOGO = "path/to/logo.png"
BG_MUSIC = "path/to/background_music.mp3"

YOUTUBE_SECRETS = "path/to/client_secrets.json"
```

Optional settings:

```python
DIFFICULTY_LEVEL = "beginner"   # beginner | intermediate | advanced
SCHEDULE_HOURS_AHEAD = 1
```

---

## ▶️ Usage

Run the script:

```bash
python master_run.py
```

---

## 📁 Output

* Final rendered video (temporary directory)
* Automatically uploaded to YouTube
* Scheduled publish (default: +1 hour)

---

## 🔄 Workflow Overview

```
[1] Generate Word (Groq API)
        ↓
[2] Download Images
        ↓
[3] Generate Audio (TTS engines)
        ↓
[4] Render Video (FFmpeg)
        ↓
[5] Upload to YouTube
```

---

## 🛠 Requirements

* Python 3.8+
* FFmpeg installed (or `ffmpeg.exe` in script directory)
* Internet connection
* YouTube API credentials

---

## 📌 Key Improvements (v10)

* ✅ Dynamic comment prompt segment (Segment 7)
* ✅ Audio sync fixed (consistent 44100 Hz processing)
* ✅ Better engagement scripting
* ✅ Stable video/audio merging pipeline

---

## ⚠️ Notes

* Ensure `ffmpeg` is accessible (PATH or local file)
* First run will authenticate YouTube (OAuth flow)
* Temporary files are auto-cleaned after execution

---

## 💡 Example Output

* Word: *Schule*
* Meaning: School
* Includes:

  * Voice narration (German + English)
  * Example sentence
  * Interactive comment challenge

---

## 📜 License

Personal / educational use. Modify as needed.

---

## ✨ Future Ideas

* Multi-language support
* Subtitle overlays (SRT)
* Batch video generation
* Analytics-based word selection

---

## 👨‍💻 Author

Rahul Gowda

---

Enjoy building your automated language learning channel! 🚀
