# Taragon — landing site

A single-page site: a hero, a private file-drop, and a contact form.
Plain HTML/CSS/JS — **no build step, no dependencies.** Open `index.html` to preview locally.

## Why Netlify (and not GitHub Pages)
GitHub Pages can only serve static files — it **cannot receive uploads**. Netlify deploys
the *same* GitHub repo for free **and** captures form/file submissions into a private
dashboard. Your visitors' files never touch the public repo.

---

## Put it live in ~10 minutes

### 1 — Push to GitHub
1. Create a new repo at https://github.com/new → name it `taragon-site` → **Create repository**
   (leave it empty — no README, since we already have one).
2. In this folder, run:
   ```bash
   git init
   git add .
   git commit -m "Taragon landing site"
   git branch -M main
   git remote add origin https://github.com/<YOUR-USERNAME>/taragon-site.git
   git push -u origin main
   ```
   *(If `git` asks you to sign in, use your GitHub username + a Personal Access Token as the password: GitHub → Settings → Developer settings → Personal access tokens.)*

### 2 — Deploy on Netlify
1. Sign up free at https://app.netlify.com using **“Log in with GitHub.”**
2. **Add new site → Import an existing project → GitHub →** pick `taragon-site`.
3. Leave build settings empty, click **Deploy**. You'll get a live URL like
   `taragon-site.netlify.app` in ~30 seconds.

### 3 — Turn on file uploads
- Netlify auto-detects the two forms in `index.html` on deploy.
- Submissions (incl. uploaded files) appear under **Site → Forms** in your Netlify dashboard.
- Optional: **Forms → Settings → Form notifications → add email** to get pinged on every submission.

### 4 — Connect your domain
1. Netlify → **Domain management → Add a domain** → type your domain.
2. Either point your registrar's nameservers to Netlify (easiest — Netlify shows you which),
   or add the `CNAME`/`A` records Netlify lists. HTTPS is automatic and free.

---

## Editing later
- All copy, colors, and layout live in `index.html`.
- **Your real logo:** save it as `logo.png` in this folder, then in `index.html` swap the
  nav `<svg>…</svg>` for `<img src="logo.png" alt="Taragon" style="width:24px">`
  (a comment marks the spot). Push, and Netlify redeploys automatically.

## Free-tier limits (plenty for a launch)
Netlify free: 100 form submissions/month and file uploads up to ~10 MB each. Upgrade if you outgrow it.

## Don't want Netlify?
You can host on GitHub Pages and route the forms through a free service like
[Web3Forms](https://web3forms.com) or [Formspree](https://formspree.io) — files then arrive
as email attachments instead of a dashboard. Netlify is simpler, so it's the default here.
