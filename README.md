# 📡 YouTube-First Sermon Publishing Automation (n8n Workflow)

This repository contains a no-code/low-code workflow built with **n8n** as part of my internship. The goal is to automate a **YouTube-first content publishing pipeline** for sermons or devotional media — reducing manual tasks, improving turnaround time, and increasing consistency across platforms.

![AI Workflow Automation](https://github.com/user-attachments/assets/b8c6edb6-0959-4e35-b7a8-3e0b8129520d)

---

## ✨ Project Overview

This workflow automates the process of receiving a sermon submission, downloading the associated YouTube video, transcribing the audio, and publishing a complete blog post (with embedded video and formatted transcript) on WordPress.

---

## ✅ Current Workflow

### 🔁 Step-by-step Flow:

1. **Form Submission** – A user submits a form with details and a YouTube link.  
2. **Google Sheets Logging** – The submitted data is appended to a Google Sheet.  
3. **YouTube Metadata** – Metadata is fetched from the video to confirm it exists and extract the video ID.  
4. **Video Download** – The audio from the YouTube video is downloaded via a self-hosted mp3 microservice (powered by `yt-dlp`).  
5. **Transcription** – The audio file is sent to the [Groq API](https://groq.com) for transcription using an open LLM.  
6. **Formatting** – The transcript is passed to the OpenAI API (`gpt-3.5-turbo`) to be structured into clean HTML paragraphs.  
7. **Post Publishing** – A WordPress post is created using the sermon title, YouTube embed, and formatted transcript.

---

## ⚙️ Tools & Technologies

- **n8n** – Workflow automation platform  
- **YouTube Data API** – To fetch metadata and validate video IDs  
- **Self-hosted yt-dlp microservice** – Converts YouTube videos to mp3  
- **Groq API** – Transcribes the mp3 using efficient LLMs  
- **OpenAI GPT-3.5** – Formats raw transcription into HTML  
- **WordPress REST API** – Creates a blog post with the video and formatted transcript  
- **Google Sheets** – Logs each submission for tracking  
