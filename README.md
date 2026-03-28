# Email Agent — Deployment Guide

## How to get your personal URL (e.g. `yourname.github.io/email-agent`)

This takes about 5 minutes. No coding knowledge needed.

---

## Step 1 — Create a free GitHub account
Go to https://github.com/signup and create a free account if you don't have one.

---

## Step 2 — Create a new repository
1. Click the **+** button (top right) → **New repository**
2. Name it: `email-agent`
3. Set it to **Public**
4. Check **"Add a README file"**
5. Click **Create repository**

---

## Step 3 — Upload the HTML file
1. In your new repository, click **Add file → Upload files**
2. Upload the `email_agent_final.html` file
3. **Rename it to `index.html`** (important!)
4. Click **Commit changes**

---

## Step 4 — Enable GitHub Pages
1. Go to your repository → **Settings** tab
2. Scroll to **Pages** (left sidebar)
3. Under **Source**, select **Deploy from a branch**
4. Branch: **main**, folder: **/ (root)**
5. Click **Save**

Wait ~2 minutes, then your app is live at:
`https://YOUR_USERNAME.github.io/email-agent/`

---

## Step 5 — Set up Google OAuth (add your GitHub Pages URL)
1. Go to https://console.cloud.google.com/apis/credentials
2. Find your OAuth 2.0 Client ID → click Edit
3. Under **Authorized redirect URIs**, add:
   `https://YOUR_USERNAME.github.io/email-agent/`
4. Under **Authorized JavaScript origins**, add:
   `https://YOUR_USERNAME.github.io`
5. Save

---

## Step 6 — First launch
1. Open your URL: `https://YOUR_USERNAME.github.io/email-agent/`
2. Enter your Gemini API key and OAuth Client ID
3. Click **Save & Launch**
4. Done — keys are saved forever in your browser

Next time you visit, it goes straight to the app. No login, no passwords.

---

## Updating the app in the future
Just upload a new `index.html` to GitHub — the site updates automatically.

---

## Your keys are safe
- Keys are stored in `localStorage` — only in YOUR browser on YOUR device
- They are never sent to any server (not GitHub, not anyone)
- To use on another device/browser, go to Settings ⚙ and enter them once

---

## Quick links
- Gemini API key: https://aistudio.google.com/apikey
- Google Cloud Console: https://console.cloud.google.com/apis/credentials
- GitHub: https://github.com
