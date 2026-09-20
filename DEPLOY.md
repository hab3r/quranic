# Deployment Guide

## One-time setup

### 1. Install GitHub CLI

```bash
winget install GitHub.cli
```

### 2. Authenticate

Create a `.env` file in this folder (copy from `.env.example`) and paste your GitHub Personal Access Token.

Then run:

```bash
cd C:\Users\me10_\OneDrive\Desktop\quranic
```

Authenticate with your token (paste it when prompted, then press Enter):

```bash
gh auth login --with-token
```

Or use git directly:

```bash
git remote set-url origin https://hab3r:YOUR_TOKEN@github.com/hab3r/quranic.git
```

### 3. Push to GitHub

```bash
git push -u origin main
```

### 4. Enable GitHub Pages

Go to https://github.com/hab3r/quranic/settings/pages and set:
- **Source**: Deploy from a branch
- **Branch**: main / (root)

The site will be live at: **https://hab3r.github.io/quranic/**

### 5. Update URLs

Replace `USERNAME` with `hab3r` in:
- `sitemap.xml` — all `<loc>` entries
- `robots.txt` — the Sitemap line

## Updating the site

After making changes:

```bash
git add .
git commit -m "Update site"
git push
```

GitHub Pages will redeploy automatically within a few minutes.
