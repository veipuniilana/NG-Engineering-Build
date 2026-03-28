# NG Engineering & Build

Marketing site for NG Engineering & Build. Static files live in `public/`; `server.js` serves them locally with Express (`npm start`).

## Push to GitHub (HTTPS — `veipuniilana`)

Remote is HTTPS:

```text
https://github.com/veipuniilana/NG-Engineering-Build.git
```

1. Create a **Personal Access Token** (classic): GitHub → **Settings → Developer settings → Personal access tokens** → generate with **`repo`** scope. Copy it once (GitHub won’t show it again).
2. Push:

```bash
cd Construction_Website
git push -u origin main
```

3. If macOS prompts for credentials: **Username** = `veipuniilana`, **Password** = the token (not your GitHub password).

To clear a wrong saved login: Keychain Access → search `github` → remove `github.com` entries, then push again.

Alternatively: `gh auth login` → HTTPS → paste token when asked.

## Host on GitHub Pages

This repo includes [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml). After `main` is pushed:

1. On GitHub: **Settings → Pages → Build and deployment**.
2. Under **Source**, select **GitHub Actions** (not “Deploy from a branch”).
3. The **Deploy GitHub Pages** workflow will run on each push to `main`.
4. The site will be available at **https://veipuniilana.github.io/NG-Engineering-Build/**

Asset links in `public/index.html` use **relative** paths so CSS and images load correctly under that project URL.

## Local preview

```bash
npm install
npm start
```

Open http://localhost:3000 (or the `PORT` you set).

## Netlify (alternative)

If you prefer Netlify: connect the repo, set **Publish directory** to `public`, **Build command** empty. For Express on Netlify you’d need a serverless adapter; static hosting of `public/` is enough for this site.
