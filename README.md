# 📓 Lexis — AI-Powered Smart Notes

> Generate comprehensive ~1000-word exam notes on any topic in **English and Hinglish**, with instant switching between **bullet-point** and **paragraph** formats. Built on the Anthropic Claude API.

![Lexis Banner](https://img.shields.io/badge/Lexis-Smart%20Notes-9d8fff?style=for-the-badge&logo=bookstack&logoColor=white)
![Claude API](https://img.shields.io/badge/Powered%20by-Claude%20API-c4b5fd?style=for-the-badge&logo=anthropic&logoColor=white)
![HTML](https://img.shields.io/badge/Built%20with-HTML%20%2F%20CSS%20%2F%20JS-6ee7b7?style=for-the-badge&logo=html5&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-fbbf24?style=for-the-badge)

---

## ✨ Features

- **AI-generated notes** — Enter any topic and get ~1000-word structured exam notes instantly using the Claude API
- **15-mark exam format** — Each note follows a university-grade answer structure with introduction, sections, subtopics, and an exam tip
- **English + Hinglish** — Every note is generated in both formal English and natural Roman-script Hinglish simultaneously
- **Dual view modes** — Switch between **bullet-point** view (quick revision) and **paragraph** view (deep reading) per subtopic
- **Rich subtopic expansion** — Each section breaks down into 2–3 subtopics with dedicated paragraphs and bullet points
- **Persistent storage** — All notes are auto-saved via `window.storage` and persist across sessions
- **Live search** — Filter saved notes in real time via the sidebar search bar
- **Word count stats** — Displays live word count, section count, and subtopic count per note
- **Dark editorial UI** — `DM Serif Display` headings, `Instrument Sans` body, `DM Mono` metadata, purple accent design system

---

## 🖥️ Demo

| View | Description |
|------|-------------|
| **Bullet Mode** | Quick revision — each subtopic shown as scannable bullet points with bold key terms |
| **Paragraph Mode** | Deep reading — each subtopic rendered as a dense academic paragraph |
| **Hinglish Toggle** | Switch the entire note to natural Roman-script Hindi-English mix |

---

## 🚀 Getting Started

### Prerequisites

- A modern browser (Chrome, Firefox, Edge, Safari)
- Access to the **Anthropic Claude API** (handled automatically when running inside Claude.ai artifacts)

### Running Locally

If running outside Claude.ai, you'll need to wire up the Anthropic API key yourself:

```bash
# Clone the repo
git clone https://github.com/<your-username>/lexis.git
cd lexis
```

Then open `index.html` in your browser. For API calls to work outside Claude.ai, add your key to the fetch headers:

```js
headers: {
  "Content-Type": "application/json",
  "x-api-key": "YOUR_ANTHROPIC_API_KEY",
  "anthropic-version": "2023-06-01"
}
```

> **Note:** When running inside Claude.ai artifacts, the API key is injected automatically — no setup needed.

---

## 📁 Project Structure

```
lexis/
├── index.html      # Single-file app — HTML + CSS + JavaScript
└── README.md       # This file
```

Lexis is intentionally a **single-file application** — no build tools, no npm, no bundler. Just open and use.

---

## 🧠 How It Works

```
User enters topic
       │
       ▼
Claude API (claude-sonnet-4)
       │
       ▼
JSON response:
  ├── english
  │     ├── intro
  │     ├── sections[]
  │     │     └── subtopics[]
  │     │           ├── paragraph  ← paragraph view
  │     │           └── bullets[]  ← bullet view
  │     └── tip
  └── hinglish (same structure)
       │
       ▼
Rendered in UI with language + format toggles
       │
       ▼
Auto-saved to window.storage (persists across sessions)
```

---

## 🎨 Design System

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#0f0e11` | App background |
| `--accent` | `#9d8fff` | Primary purple |
| `--accent2` | `#c4b5fd` | Hover / active states |
| `--green` | `#6ee7b7` | Badges, success |
| `--amber` | `#fbbf24` | Exam tip highlight |
| `--serif` | DM Serif Display | Headings / note titles |
| `--sans` | Instrument Sans | Body text / UI |
| `--mono` | DM Mono | Metadata / labels / code |

---

## 🛠️ Tech Stack

| Technology | Role |
|------------|------|
| **Vanilla HTML/CSS/JS** | Single-file frontend — no framework |
| **Anthropic Claude API** | Note generation (`claude-sonnet-4`) |
| **`window.storage`** | Persistent note storage across sessions |
| **Google Fonts** | DM Serif Display, Instrument Sans, DM Mono |

---

## 📝 Prompt Engineering

The system prompt instructs Claude to return a strict JSON schema with:

- ~1000 words per language
- 4–6 main sections per note
- 2–3 subtopics per section
- Each subtopic has **both** a paragraph version and a bullets array
- Key terms bolded with `**double asterisks**`
- Natural Hinglish in Roman script (not transliteration)
- One actionable exam-writing tip per note

---

## 🗺️ Roadmap

- [ ] Export notes as PDF
- [ ] Markdown export
- [ ] Custom word-count target (600 / 1000 / 1500 words)
- [ ] Tag and categorize notes by subject
- [ ] Share notes via link
- [ ] Offline support with Service Workers
- [ ] Mobile-responsive layout

---

## 👤 Author

**Aayush**
B.Tech Data Science · Maharishi Dayanand University, Rohtak
BA (Hons.) English · School of Open Learning, Delhi University

Built as part of an AI-powered study tools portfolio alongside the **Academic Risk Prediction** project.

---

## 📄 License

This project is licensed under the **MIT License** — free to use, modify, and distribute.

---

> *"The best notes aren't the ones you copy — they're the ones that make you think."*
