# Sentira

Marketing site for **Sentira** — an AI consultancy (strategy, engineering, adoption).
Static site, zero build step, zero dependencies. Deploys anywhere that serves static files.

Intended domain: **sentira.si** (in registration).

## Structure

```
.
├── site/
│   ├── assets/
│   │   ├── favicon.svg
│   │   ├── hero-nobg.png # active hero image
│   │   ├── hero.jpg      # retained source image
│   │   └── og.svg        # social share image
│   ├── index.html        # single-page site and copy
│   ├── main.js           # navigation and scroll interactions
│   ├── netlify.toml      # deployment and response headers
│   ├── robots.txt
│   ├── sitemap.xml
│   └── styles.css        # design system and responsive layout
├── .gitignore
└── README.md
```

## Run locally

Any static server works. For example:

```bash
python3 -m http.server 8080 --directory site
# open http://localhost:8080
```

## Deploy to Netlify

**Option A — CLI (fastest):**

```bash
cd site
npx netlify-cli deploy --dir . --prod
```

First run opens a browser to authenticate and lets you create/link a site.

**Option B — Drag & drop:** zip or drag the `site` folder into
https://app.netlify.com/drop.

**Option C — Git:** push the repo and connect it in Netlify. Build command: _none_.
Base directory: `site`. Publish directory: `.`.

## Connect the domain

Once `sentira.si` is active, in Netlify → Domain settings → add custom domain,
then point the registrar's nameservers (or a CNAME/A record) at Netlify.
Netlify provisions HTTPS automatically.

## Editing

All text lives in `site/index.html`. Colors and spacing are CSS variables at the
top of `site/styles.css` (`--grad`, `--bg`, `--text`, etc.).
