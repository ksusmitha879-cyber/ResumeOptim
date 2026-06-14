# ResumeOptim
# 🔥 Resume Roaster & Optimizer

A dual-mode AI career tool that either ruthlessly and hilariously critiques a resume for entertainment, or provides actionable professional feedback with before/after rewrites to help land a job.

![Powered by Claude](https://img.shields.io/badge/Powered%20by-Claude%20AI-7F77DD?style=flat-square) ![Netlify](https://img.shields.io/badge/Deployed%20on-Netlify-00C7B7?style=flat-square)

---

## Demo

> **Input:** "I did stuff with Excel and made reports."
>
> **🔥 Roast output:** "Oh, you 'did stuff' with Excel? What, did you color the cells green and call it a financial model? This bullet point is so weak it needs a personal trainer."
>
> **🚀 Optimize output:**
> BEFORE: I did stuff with Excel and made reports
> AFTER: Developed automated Excel dashboards tracking 15+ KPIs, reducing weekly reporting time by 40%

---

## Deployed Link - https://golden-panda-8a21cd.netlify.app

## Features

- Dual mode — Roast (savage comedy) and Optimize (professional rewrites)
- Roast mode attacks the writing, never the person
- Optimize mode delivers Before/After format with action verbs and implied metrics
- 3 quick-fill example presets to test instantly
- Colour-coded output — red for roast, green for optimize
- Copy to clipboard button
- Dark mode support + mobile responsive

---

## Project Structure

```
05-resume-roaster/
├── index.html
├── .gitignore
└── netlify/
    └── functions/
        └── generate.js
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Netlify CLI](https://docs.netlify.com/cli/get-started/) — `npm install -g netlify-cli`
- An [Anthropic API key](https://console.anthropic.com/)

### Local Development

```bash
git clone https://github.com/yourusername/resume-roaster.git
cd resume-roaster
netlify login
netlify dev
```

Open [http://localhost:8888](http://localhost:8888)

### Environment Variables

```
ANTHROPIC_API_KEY=sk-ant-your-key-here
```

---

## Deployment

```bash
netlify deploy --prod
```

Add `ANTHROPIC_API_KEY` in **Netlify Dashboard → Site configuration → Environment variables**, then redeploy.

---

## How It Works

```
User pastes resume bullet points + selects Roast or Optimize mode
        ↓
index.html builds mode-specific prompt → sends to /.netlify/functions/generate
        ↓
generate.js adds API key → forwards to Anthropic
        ↓
Claude either roasts the writing or rewrites it professionally
        ↓
Output displayed with colour-coded card matching the selected mode
```

---

## Prompt Templates

**Roast Mode:**
```
You are a hilariously brutally honest Fortune 500 recruiter who moonlights
as a stand-up comedian. Roast these resume bullet points with savage wit.
Attack the WRITING and the VAGUENESS — never the person.
```

**Optimize Mode:**
```
Act as a Fortune 500 recruiter. Rewrite the following resume bullet points
to include strong action verbs and imply measurable metrics.
Format as BEFORE / AFTER / WHY for each bullet.
```

---

## Guardrails

The roast prompt is carefully worded to ensure the AI:
- Attacks the **text quality**, not the person's worth or intelligence
- Stays constructive — always ends with genuine advice
- Never makes personal assumptions about the user

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Icons | Tabler Icons |
| AI Model | Claude Sonnet (claude-sonnet-4-6) |
| Backend | Netlify Serverless Functions |
| Hosting | Netlify |

---

## License

MIT
