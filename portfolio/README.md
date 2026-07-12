# Naman Agarwal — Portfolio

A single-page portfolio site: live sports dashboards, AI/ML projects, stack, and contact — built as one self-contained `index.html` (no build step, no dependencies to install).

## Structure

```
portfolio/
├── index.html                    # the entire site (HTML + CSS + JS)
└── assets/
    ├── Naman_Agarwal_Resume.docx # downloadable résumé (linked from the hero button)
    └── certificates/              # certificate PDFs, linked from the Certifications section
        ├── NPTEL_Algorithmic_Graph_Theory.pdf
        ├── NPTEL_Human_Computer_Interaction.pdf
        ├── NPTEL_Responsible_Safe_AI_Systems.pdf
        ├── Udemy_Machine_Learning_AZ.pdf
        └── Udemy_TensorFlow_Bootcamp.pdf
```


## Run it locally

Just open `index.html` in a browser — or, for a local server (needed for some browsers' download-link behavior):

```bash
cd portfolio
python3 -m http.server 8000
# visit http://localhost:8000
```

## Put it on GitHub + go live with GitHub Pages

### 1. Create the repo
- Go to [github.com/new](https://github.com/new)
- Name it `portfolio` (or `your-username.github.io` if you want it at the root of your GitHub domain — see note below)
- Keep it public, don't initialize with a README (you already have one)

### 2. Push your files

```bash
cd portfolio
git init
git add .
git commit -m "Initial commit: portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/portfolio.git
git push -u origin main
```

### 3. Turn on GitHub Pages
- On GitHub, open your repo → **Settings** → **Pages** (left sidebar)
- Under "Build and deployment" → **Source**, choose **Deploy from a branch**
- Branch: `main`, folder: `/ (root)` → **Save**
- Wait ~1 minute, then refresh the page — GitHub will show your live URL:
  `https://<your-username>.github.io/portfolio/`

### Optional: use it as your root domain site
If you name the repo exactly `<your-username>.github.io`, GitHub Pages serves it directly at `https://<your-username>.github.io` (no `/portfolio/` path). Same steps otherwise.

### Custom domain (optional)
If you own a domain, add it under **Settings → Pages → Custom domain**, and create a `CNAME` record with your DNS provider pointing to `<your-username>.github.io`.

## Updating content later

All copy — dashboard cards, academic projects, skills, certifications, education — lives in the `<script>` block at the bottom of `index.html`, in plain JS arrays (`dashboards`, `projects`, `stack`, `certs`, `education`, `tickerStats`). Edit the values there; no HTML templating knowledge needed. Then:

```bash
git add index.html
git commit -m "Update portfolio content"
git push
```

GitHub Pages redeploys automatically within a minute or two of every push to `main`.
