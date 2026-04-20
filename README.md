# Communication & Language Studies — Vercel Deployment Guide

## Project Structure
```
vercel-project/
├── api/
│   └── claude.js        ← Secure backend (hides your API key)
├── public/
│   └── index.html       ← The full learning platform frontend
├── vercel.json          ← Routing configuration
└── README.md
```

---

## Step-by-Step Deployment

### Step 1 — Get Your Anthropic API Key
1. Go to https://console.anthropic.com
2. Sign up or log in
3. Click **API Keys** in the left sidebar
4. Click **Create Key**, give it a name, copy the key
5. Keep it safe — you'll need it in Step 4

---

### Step 2 — Create a GitHub Repository
1. Go to https://github.com and sign in (or create a free account)
2. Click the **+** button → **New repository**
3. Name it e.g. `comm-lang-studies`
4. Set it to **Private** (recommended) or Public
5. Click **Create repository**
6. Upload all three files/folders:
   - `api/claude.js`
   - `public/index.html`
   - `vercel.json`

   You can drag-and-drop them into GitHub's file uploader.

---

### Step 3 — Deploy to Vercel
1. Go to https://vercel.com and sign up with your GitHub account
2. Click **Add New Project**
3. Select your `comm-lang-studies` repository
4. Vercel will auto-detect the settings — **don't change anything**
5. Click **Deploy** (wait ~1 minute)

---

### Step 4 — Add Your API Key (Environment Variable)
This is the most important step — it keeps your key secret.

1. In your Vercel project dashboard, click **Settings**
2. Click **Environment Variables** in the left menu
3. Add a new variable:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** paste your `sk-ant-...` key
   - **Environment:** select All (Production, Preview, Development)
4. Click **Save**
5. Go to **Deployments** → click the three dots on your latest deployment → **Redeploy**

---

### Step 5 — Your Site is Live!
Vercel gives you a URL like:
`https://comm-lang-studies.vercel.app`

Share this URL with your students. That's it!

---

## Updating the Site
Whenever you change `index.html` or `claude.js` and push to GitHub,
Vercel automatically redeploys within ~1 minute.

---

## Cost Estimate
- **Vercel hosting:** Free (Hobby plan)
- **Anthropic API:** ~$0.01–0.02 per student per topic session
- New Anthropic accounts get **$5 free credit**
- For a class of 50 students completing all chapters: ~$10–15 total

---

## Troubleshooting
| Problem | Fix |
|---|---|
| "API key not configured" | Re-check Step 4 and redeploy |
| Lessons not loading | Check Vercel function logs in dashboard |
| 401 error | Your API key is invalid or expired — create a new one |
| Slow loading | Normal — AI generation takes 5–15 seconds per request |
