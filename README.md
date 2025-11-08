# ReactorSim — Educational Web Reactor Simulator

**Demo**: single-file client-side reactor simulator (HTML/JS/CSS). Educational, gamified, and intentionally simplified.
**License**: MIT — feel free to fork and adapt.

## What's included
- `index.html` — single-file prototype (UI + toy physics), drop into GitHub Pages or cPanel.
- `README.md` — this file.
- `LICENSE` — MIT
- `.github/workflows/deploy.yml` — GitHub Actions workflow to auto-deploy to GitHub Pages.
- `CNAME` — optional: contains the custom subdomain to use (replace with your subdomain).

## Quick start — publish to GitHub (recommended)
1. Create a new repo on GitHub (e.g. `reactorsim`). You can do this on the website or from CLI:
   ```bash
   gh repo create yourusername/reactorsim --public --source=. --remote=origin
   ```
   or use manual git commands below.

2. If you're not using the `gh` CLI, run these from the repo root:
   ```bash
   git init
   git add .
   git commit -m "Initial ReactorSim prototype"
   git branch -M main
   git remote add origin https://github.com/<yourusername>/reactorsim.git
   git push -u origin main
   ```

3. GitHub Actions in `.github/workflows/deploy.yml` will build and deploy to **gh-pages** branch automatically on push to `main`. Pages will be served at `https://<yourusername>.github.io/reactorsim/` or your custom domain if configured.

## Use a custom subdomain (example: `sim.congmc.com`)
- In this repo there's a `CNAME` file. Replace its contents with your desired subdomain:
  ```
  sim.congmc.com
  ```
- Commit & push; GitHub Pages reads `CNAME` and registers the custom domain for the Pages site.

- Then configure DNS at your domain registrar or Cloudflare:
  - For a subdomain (recommended): create a **CNAME** record:
    - Name: `sim` (for `sim.congmc.com`)
    - Value: `<yourusername>.github.io.` (for example `congmc.github.io.`) — point to your GitHub Pages username domain.
  - For apex/root domains you must add A records to GitHub Pages IPs (see GitHub Pages docs).

- If you're using Cloudflare, set the CNAME to **DNS only** (not proxied) — the orange cloud should be **off** for GitHub Pages to work properly with custom domains or use Cloudflare Pages instead.

## Deploy workflow details
- The included `.github/workflows/deploy.yml` uses `peaceiris/actions-gh-pages` to push the built site to `gh-pages` branch.
- It's configured to deploy the repo root (so the single `index.html` will be served).

## cPanel upload alternative
1. Unzip and upload `index.html` to `public_html/reactorsim/` or any folder you want.
2. Visit `https://yourdomain.tld/reactorsim/index.html` to open it.
3. To use a subdomain (e.g. `sim.congmc.com`), create that subdomain in cPanel (Domains → Subdomains), point its document root to your folder, and upload `index.html` there.

## Security & disclaimer
This is a **toy simulator for learning and entertainment**. It deliberately avoids realistic technical parameters and must **not** be used to learn real reactor operation or construction. The authors are not responsible for misuse.

## Want me to push and set up repo for you?
I can't push to GitHub or change DNS directly, but I can:
- generate the repo files (done),
- give you the exact git/gh commands to run (see above),
- craft PR templates, issues, or CI changes,
- or produce a shell script to run locally to create the repo and push (if you give me your GitHub repo URL or username).

----
Made with chaotic love by your ReactorSim wingman 🐧🔥
