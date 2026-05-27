# 🤖 Auto Contribution Bot

**Status:** <span style="color:limegreen;">● LIVE & WORKING</span>  
**Maintained by:** Naboraj Sarkar (Nishant)  
**Category:** GitHub Automation • Dev Tools • Productivity  
**Vibe:** 🎮 Gaming × 💻 Code × 🤖 Automation × 💙 Blue Energy

---

## 🔥 What This Bot Does

Auto Contribution Bot is a lightweight GitHub Actions automation system that safely maintains your GitHub contribution streak with realistic, low-frequency daily commits.

Designed for developers, students, creators, and gamers who value consistency, the bot automatically updates a log file using scheduled GitHub workflows while keeping activity natural and reliable.

### ✨ Features

- ✅ Fully automated daily GitHub contributions
- 🔁 Built-in fallback schedule for streak protection
- 🛡️ Retry logic for failed pushes
- 🎲 Randomized execution delay for human-like timing
- 🧠 Duplicate protection (prevents multiple commits/day)
- 🌍 IST timezone support (`Asia/Kolkata`)
- 🔐 Uses secure built-in `GITHUB_TOKEN`
- ⚡ Zero maintenance after setup
- 📈 Helps maintain contribution consistency naturally
---

## 🧠 How It Works (Technical Breakdown)

1. GitHub Actions schedules a daily trigger (07:00 UTC ≈ 12:30 PM IST).
2. Repo is checked out securely.
3. Applies a random delay to avoid patterns.
4. Appends a timestamped line to `log.txt` (in IST timezone).
5. Commits and pushes using your details for authentic contributions.

The workflow includes fallback scheduling and retry protection to reduce the chances of missed contribution days.

---
---

## 🛡️ Reliability System

This bot is designed with streak protection in mind.

### Protection Features
- Dual scheduled runs daily
- Automatic push retries
- Remote sync before push
- Duplicate-day detection
- Randomized timing patterns

### Why This Matters
GitHub Actions scheduled workflows can occasionally delay or skip runs during platform load spikes.  
The fallback system helps ensure your contribution streak survives temporary scheduler failures.
---

## 📁 Project Structure

```
.github/
 └── workflows/
     └── daily.yml (the magic automation file)
log.txt (daily updated log file)
README.md (this file)
```

---

## 🚀 Quick Setup Guide

### 1️⃣ Create a New Repo
- Make it public or private (both work for contributions).
- Use `main` as the default branch.

### 2️⃣ Add the Workflow File
Create `.github/workflows/daily.yml` and paste this:

```yaml
name: Daily Contribution

permissions:
  contents: write

on:
  schedule:
    - cron: '0 7 * * *'  # 07:00 UTC ≈ 12:30 PM IST
  workflow_dispatch:

jobs:
  auto-contribute:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Random delay (0–2 hours, more natural)
        run: sleep $((RANDOM % 7200 + 300))  # min 5 min delay

      - name: Make daily commit (IST timezone)
        run: |
          export TZ=Asia/Kolkata

          # Safety: create file if missing
          touch log.txt

          # Append fresh line with timestamp
          echo "Daily auto update: $(date '+%Y-%m-%d %H:%M:%S %Z')" >> log.txt

          git config user.name "NABORAJ SARKAR"
          git config user.email "nishant.ns.business@gmail.com"

          git add log.txt

          # Commit only if changes exist
          git diff --staged --quiet || git commit -m "chore: daily contribution $(date '+%Y-%m-%d')"

          git push origin HEAD
```

### 3️⃣ Commit and Push
Push the file to `main`. Boom—the bot's live!

**Pro Tip:** Verify your email (`nishant.ns.business@gmail.com`) is added in GitHub Settings > Emails. For private repos, enable "Include private contributions" in your profile settings.

---

## 🧪 Testing It Out
- Head to your repo's **Actions** tab.
- Select **Daily Contribution**.
- Click **Run workflow** (manual trigger).
- Watch the logs—success means a new commit and green square in 5–30 mins.

---

## ⏰ Timing Details

### Primary Run
- 07:00 UTC → 12:30 PM IST

### Backup Run
- 15:00 UTC → 8:30 PM IST

### Commit Timing
A randomized delay makes execution feel more natural while still remaining reliable.
---

## ⚠️ Warnings & Ethics
- This is for **genuine consistency**, not faking skills.
- Stick to one commit/day—don't spam or loop.
- Over-automation can flag as unnatural; keep it subtle.
- Real code > green squares. Use this to build habits, not hype.

Automation rocks, but pair it with actual projects for that true gamer-dev win.

---

## 🎮 Gaming × Developer Vibe
Built by a Siliguri-based Hindu Bengali dev who loves blue vibes 💙. I believe in:
- ⚡ Systems that level up your grind.
- 🎯 Automation to free up time for gaming and coding.
- 🧠 Consistency as the ultimate power-up.

---

## 🌐 About Me & Socials
**Naboraj Sarkar (Nishant)**  
Student • Developer • Gamer • Content Creator from Siliguri, West Bengal, India.

- 🌐 Website: [nsgamming.xyz](https://nsgamming.xyz)
- 🐙 GitHub: [NABORAJ'S](https://github.com/naborajs)
- ▶️ YouTube: [NS GAMMiNG](https://youtube.com/@Nishant_sarkar)
- 📸 Instagram: [@NABORAJ SARKAR](https://instagram.com/naborajs)
- 🐦 X (Twitter): [@NSGAMMING699](https://x.com/NSGAMMING699)
- 💬 Telegram: [@nsgamming69](https://t.me/nsgamming69)
- 💼 LinkedIn: [Naboraj Sarkar](https://linkedin.com/in/naboraj-sarkar)

---

## 🔍 SEO Keywords
GitHub automation, auto contribution bot, GitHub Actions daily commit, developer productivity tools, coding streak maintainer, natural GitHub contributions, automation for devs, NS CODEX projects, Naboraj Sarkar developer, Nishant Sarkar GitHub, developer consistency tool.
