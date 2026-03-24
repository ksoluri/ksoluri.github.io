# Kelly Soluri — Personal Website

A cartographic, earthy personal portfolio site built with plain HTML, CSS, and a touch of JavaScript. No frameworks, no build tools — just files you can edit and deploy in minutes.

**Live at:** `https://kellysoluri.github.io`

---

## Pages

| Page | File | Description |
|---|---|---|
| Homepage | `index.html` | Bento-style grid linking all sections |
| Maps | `pages/maps.html` | Leaflet.js embed + map gallery |
| Papers | `pages/papers.html` | Publications with type filter |
| Projects | `pages/projects.html` | Coding + personal projects |
| Blog | `pages/blog.html` | Post list with featured entry |
| Thought of the day | `pages/thought.html` | Living /now-style personal snapshot |
| Collaboration | `pages/collab.html` | Offer cards + contact form |

---

## Deploying to GitHub Pages — step by step

### Step 1: Create your GitHub account (if you don't have one)

Go to [github.com](https://github.com) and sign up. Your username will become part of your site URL, so choose it carefully — ideally `kellysoluri`.

---

### Step 2: Create the repository

1. Log in to GitHub and click the **+** icon in the top-right corner → **New repository**
2. Name it exactly: `ksoluri.github.io`
   - This special naming convention tells GitHub to treat it as your personal site
   - It must match your username exactly (e.g. if your username is `kellysoluri`, the repo is `ksoluri.github.io`)
3. Set it to **Public** (required for free GitHub Pages hosting)
4. Leave all other options unchecked — do **not** add a README, .gitignore, or license now
5. Click **Create repository**

---

### Step 3: Upload your files

You have two options:

#### Option A — Upload via the GitHub website (easiest, no Git required)

1. On your new empty repository page, click **uploading an existing file**
2. Open the `kelly-soluri-site` folder on your computer
3. Select all files and folders inside it and drag them into the upload area
   - You must include: `index.html`, the `assets/` folder, and the `pages/` folder
4. Scroll down, write a short commit message like `Initial site upload`
5. Click **Commit changes**

#### Option B — Upload via Git (recommended for ongoing edits)

If you have Git installed, open your terminal and run:

```bash
# Navigate into the unzipped site folder
cd path/to/kelly-soluri-site

# Initialise Git
git init

# Connect to your GitHub repository
git remote add origin https://github.com/ksoluri/ksoluri.github.io.git

# Stage all files
git add .

# Make your first commit
git commit -m "Initial site upload"

# Push to GitHub
git push -u origin main
```

> **Tip:** If asked for your password, GitHub now uses Personal Access Tokens instead of passwords.
> Go to GitHub → Settings → Developer settings → Personal access tokens → Generate new token.
> Give it `repo` scope and use it as your password.

---

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (tab along the top)
3. In the left sidebar, click **Pages**
4. Under **Source**, select **Deploy from a branch**
5. Under **Branch**, select `main` and `/ (root)`
6. Click **Save**

GitHub will show a banner: *"Your site is being published at https://ksoluri.github.io"*

It takes **1–3 minutes** for the site to go live. Reload the page until you see a green checkmark and your URL.

---

### Step 5: Visit your site

Open `https://k.github.io` in your browser. You should see your homepage.

If you see a 404 error, wait another minute and hard-refresh (`Cmd+Shift+R` on Mac, `Ctrl+Shift+R` on Windows).

---

### Step 6 (optional): Add a custom domain

If you want `kellysoluri.com` instead of `kellysoluri.github.io`:

1. Buy a domain from a registrar (Namecheap, Google Domains, or Squarespace Domains are reliable)
2. In your domain registrar's DNS settings, add these records:

   | Type | Name | Value |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | ksoluri.github.io |

3. Back in GitHub → Settings → Pages → Custom domain: type `kellysoluri.com` and click Save
4. Check **Enforce HTTPS** (may take up to 24 hours to activate)

---

## Customising your content

### Things to update before publishing

Search each file for these placeholders and replace them with your real information:

| Placeholder | What to replace it with |
|---|---|
| `kelly@example.com` | Your real email address |
| `https://github.com/kellysoluri` | Your GitHub profile URL |
| `https://scholar.google.com` | Your Google Scholar profile URL |
| `https://linkedin.com` | Your LinkedIn profile URL |
| `[your field]` | Your research field (e.g. "hydrology") |
| `[your institution]` | Your university or organisation |
| `[location]` | Field site or city names in blog posts |

### Updating the contact form

The collaboration page uses [Formspree](https://formspree.io) for the contact form — it's free for up to 50 submissions/month, no server required.

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Create a new form and copy your form ID (it looks like `xpzgkwry`)
3. In `pages/collab.html`, find this line:
   ```html
   <form class="contact-form" action="https://formspree.io/f/your-form-id" method="POST">
   ```
4. Replace `your-form-id` with your actual ID

### Updating the Leaflet map

In `pages/maps.html`, the map is pre-centered on Washington, DC with placeholder pins. To add your own locations, find the script block at the bottom of the file and edit the `L.circleMarker` lines:

```javascript
// Format: L.circleMarker([latitude, longitude], markerStyle)
L.circleMarker([38.9, -77.0], markerStyle)
  .addTo(map)
  .bindPopup('<strong>Field site name</strong><br>Brief note.');
```

You can find lat/lon coordinates for any location at [latlong.net](https://www.latlong.net).

### Updating "Thought of the day"

`pages/thought.html` is designed to be edited directly and often — it's your living document. There's no database or CMS involved. Just open the file, update the text inside the `<blockquote>`, `<p>` tags, and the `now-list` items, then re-upload or push to GitHub.

**To update via GitHub's web editor (no Git needed):**
1. Go to your repository on GitHub
2. Navigate to `pages/thought.html`
3. Click the pencil icon (Edit this file)
4. Make your changes
5. Click **Commit changes** — your site updates within 1–2 minutes

---

## File structure

```
kellysoluri.github.io/
│
├── index.html                  ← Homepage
│
├── assets/
│   ├── css/
│   │   ├── palette.css         ← Color tokens, typography, CSS variables
│   │   ├── main.css            ← Nav, hero, grid, footer, buttons
│   │   ├── papers.css          ← Publications page
│   │   ├── projects.css        ← Projects page
│   │   ├── maps.css            ← Maps page
│   │   ├── blog.css            ← Blog page
│   │   ├── thought.css         ← Thought of the day page
│   │   └── collab.css          ← Collaboration page
│   └── js/
│       └── main.js             ← Mobile nav toggle
│
└── pages/
    ├── maps.html
    ├── papers.html
    ├── projects.html
    ├── blog.html
    ├── thought.html            ← /now-style personal snapshot
    └── collab.html
```

---

## Making edits after launch

Every time you want to update content:

**Via GitHub website:**
1. Navigate to the file you want to edit on github.com
2. Click the pencil icon → make your changes → Commit changes
3. Site updates in ~1 minute

**Via Git (faster for multiple file edits):**
```bash
# Make your edits locally, then:
git add .
git commit -m "Update thought of the day"
git push
```

---

## Colour palette reference

All colours are defined as CSS variables in `assets/css/palette.css`. The main ones:

| Variable | Value | Used for |
|---|---|---|
| `--c-parchment-50` | `#faf8f2` | Page background |
| `--c-parchment-100` | `#f5f1e8` | Card surfaces |
| `--c-ink-800` | `#2c2416` | Nav, footer, hero background |
| `--c-ink-700` | `#3d3320` | Headings |
| `--c-ink-500` | `#7a6548` | Secondary text |
| `--c-accent` | `#8c5e3c` | Links, CTAs, accents |
| `--c-terrain-water` | `#6a9fb5` | Map water tones |
| `--c-terrain-forest` | `#7a9e6b` | Map forest tones |

To change the accent colour across the whole site, update `--c-accent` and `--c-accent-light` in `palette.css`.

---

## Credits & tools used

- **Leaflet.js** — open-source interactive maps ([leafletjs.com](https://leafletjs.com))
- **Formspree** — serverless contact form ([formspree.io](https://formspree.io))
- **Google Fonts** — Playfair Display, Source Serif 4, JetBrains Mono
- **Stamen Terrain tiles** — earthy map tile style
- Inspired by the [/now page movement](https://nownownow.com) started by Derek Sivers

---

*Built with care. No frameworks harmed.*
