# GeoAI Job Mission Control

Personal job search dashboard for Purnendu Sardar — built for the Swedish GeoAI, climate tech, and environmental data engineering job market.

## Features

- **Live job feed** — pulls from Platsbanken (Arbetsförmedlingen) API, keyword-tuned to GeoAI / climate startup / data engineering tracks
- **Profile matching** — scores each job against your skills, shows matched terms and gaps
- **AI match analysis** — paste any job description (LinkedIn, company site) for Claude-powered fit analysis
- **Cover letter drafting** — AI-generated opening letter per job
- **Application tracker** — Kanban board (Saved → Applied → Interview → Offer), persists in browser
- **Skill gap heatmap** — aggregates missing skills across all viewed jobs
- **Residency countdown** — tracks your Jan 2028 PR deadline with urgency phases

---

## Deploy to GitHub Pages (5 minutes)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) → New repository
2. Name it `job-dashboard` (or anything you like)
3. Set it to **Private** (recommended — it's your personal tool)
4. Click **Create repository**

### Step 2 — Upload the file

**Option A — GitHub web UI (no command line needed):**
1. In your new repo, click **Add file → Upload files**
2. Drag and drop `index.html`
3. Click **Commit changes**

**Option B — Git command line:**
```bash
git init
git add index.html
git commit -m "Initial deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/job-dashboard.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repo → **Settings** → **Pages** (left sidebar)
2. Under **Source**, select **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)`
4. Click **Save**

GitHub will show a URL like: `https://YOUR_USERNAME.github.io/job-dashboard/`

It takes ~1 minute to go live.

### Step 4 — Add your Anthropic API key

1. Open your dashboard URL
2. Click **API Key** in the left sidebar
3. Paste your key from [console.anthropic.com](https://console.anthropic.com)
4. Click **Save**

The key is stored in your browser's `localStorage` — it never gets uploaded to GitHub.

---

## Updating the dashboard

When you want to add features or make changes:
1. Edit `index.html` locally
2. Upload the new file to GitHub (or `git push`)
3. GitHub Pages auto-redeploys in ~1 minute

---

## Moving to Vercel later (for scheduled job fetching)

When you're ready to upgrade:
- Vercel lets you add a serverless proxy function — this moves the API key to a secure environment variable instead of browser localStorage
- You can add a daily cron job that pre-fetches Platsbanken results so the dashboard loads instantly
- Ask Claude to generate the `api/proxy.js` + `vercel.json` when you're ready

---

## Notes

- Platsbanken API is public and free — no key needed for job fetching
- The `country=i46j9HoB` parameter filters to Sweden
- Jobs are re-fetched on demand (click "Fetch jobs") — no automatic refresh on GitHub Pages
- Saved jobs and API key persist in your browser's localStorage
