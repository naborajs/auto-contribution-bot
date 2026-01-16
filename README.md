<h1>🤖 Auto Contribution Bot</h1>

<p>
<b>Status:</b> <span style="color:limegreen;"><b>● LIVE & WORKING</b></span> <br>
<b>Maintained by:</b> <b>Naboraj Sarkar (Nishant)</b> <br>
<b>Category:</b> GitHub Automation • Dev Tools • Productivity <br>
<b>Vibe:</b> 🎮 Gaming × 💻 Code × 🤖 Automation
</p>

<hr>

<h2>🔥 What this bot does</h2>

<p>
Auto Contribution Bot is a lightweight GitHub Actions–powered automation that creates
<b>one safe, natural-looking contribution every day</b> to keep the GitHub contribution
graph active and consistent.
</p>

<ul>
  <li>✅ Runs automatically every day</li>
  <li>🎲 Uses a short random delay (anti-bot pattern)</li>
  <li>🟢 Keeps contribution streak alive</li>
  <li>⚙️ Zero manual effort after setup</li>
  <li>🔐 No personal access tokens required</li>
</ul>

<hr>

<h2>🧠 How it works (technical)</h2>

<ol>
  <li>GitHub Actions triggers the workflow once per day (UTC)</li>
  <li>Repository is securely checked out</li>
  <li>A random delay (0–2 hours) is applied</li>
  <li>The current timestamp is appended to <code>log.txt</code></li>
  <li>The change is committed and pushed using <code>GITHUB_TOKEN</code></li>
</ol>

<p>
The delay window is intentionally limited to avoid workflow timeouts and to ensure
<b>no day is ever skipped</b>.
</p>

<hr>

<h2>📁 Project structure</h2>

<pre>
.github/
 └── workflows/
     └── daily.yml   (automation workflow)
log.txt              (daily auto-updated file)
README.md
</pre>

<hr>

<h2>🚀 Setup / Re-Setup Guide</h2>

<h3>1️⃣ Create a GitHub repository</h3>
<ul>
  <li>Public or private (both count for contributions)</li>
  <li>Default branch must be <code>main</code></li>
</ul>

<h3>2️⃣ Create workflow file</h3>

<pre>.github/workflows/daily.yml</pre>

<pre>
name: Daily Contribution

permissions:
  contents: write

on:
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:

jobs:
  auto-contribute:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
        with:
          persist-credentials: true

      - name: Random delay
        run: sleep $((RANDOM % 7200))

      - name: Make daily commit
        run: |
          echo "Daily update: $(date)" >> log.txt
          git config user.email "action@github.com"
          git config user.name "GitHub Actions"
          git add log.txt
          git commit -m "chore: daily contribution" || echo "No changes"
          git push
</pre>

<h3>3️⃣ Commit to main</h3>
<p>That’s it. The bot is now active.</p>

<hr>

<h2>🧪 Testing</h2>

<ul>
  <li>Go to <b>Actions</b></li>
  <li>Select <b>Daily Contribution</b></li>
  <li>Click <b>Run workflow</b></li>
</ul>

<p>
A successful run creates a commit and updates <code>log.txt</code>.
</p>

<hr>

<h2>⏰ Execution timing</h2>

<ul>
  <li>Trigger time: 00:00 UTC</li>
  <li>Actual commit: random within 0–2 hours</li>
  <li>IST: approx 5:30 AM – 7:30 AM</li>
</ul>

<hr>

<h2>⚠️ Warnings & ethics</h2>

<ul>
  <li>This bot is for <b>consistency</b>, not fake productivity</li>
  <li>Do NOT increase commits to multiple times per day</li>
  <li>Do NOT spam or loop commits</li>
  <li>Over-automation can look unnatural</li>
  <li>Real projects matter more than green squares</li>
</ul>

<p>
Use responsibly.  
Automation should support learning — not replace it.
</p>

<hr>

<h2>🎮 Gaming × Developer Vibe</h2>

<p>
Built by a gamer-developer who believes in:
</p>

<ul>
  <li>⚡ Consistency over hype</li>
  <li>🎯 Systems over motivation</li>
  <li>🧠 Automation over repetition</li>
</ul>

<hr>

<h2>🌐 Branding & Socials</h2>

<p>
<b>Naboraj Sarkar (Nishant)</b><br>
Student • Developer • Gamer • Content Creator
</p>

<ul>
  <li>🌐 Website: <a href="https://nsgamming.xyz">https://nsgamming.xyz</a></li>
  <li>🐙 GitHub: <a href="https://github.com/ns-gamming">https://github.com/ns-gamming</a></li>
  <li>▶️ YouTube: <a href="https://youtube.com/@Nishant_sarkar">NS GAMMiNG</a></li>
  <li>📸 Instagram: <a href="https://instagram.com/nishant_sarkar__10k">@nishant_sarkar__10k</a></li>
  <li>🐦 X (Twitter): <a href="https://x.com/NSGAMMING699">@NSGAMMING699</a></li>
  <li>💬 Telegram: <a href="https://t.me/nsgamming69">@nsgamming69</a></li>
  <li>💼 LinkedIn: <a href="https://linkedin.com/in/naboraj-sarkar">Naboraj Sarkar</a></li>
</ul>

<hr>

<h2>🔍 SEO Keywords</h2>

<p>
GitHub automation, GitHub contribution bot, GitHub Actions automation,
developer productivity tools, coding consistency, daily GitHub commits,
automation for developers, GitHub portfolio projects, NS GAMMiNG,
Naboraj Sarkar developer
</p>
