# Portfolio — Vashok

Personal portfolio website built with **Astro** and deployed for free on **Cloudflare Pages**.

## Tech Stack

| Concern | Choice | Why |
|---------|--------|-----|
| Framework | [Astro 4](https://astro.build) | Zero JS by default, island architecture, static output |
| Styling | Vanilla CSS + custom properties | No build overhead; dark/light mode via `data-theme` |
| Fonts | Inter + Fira Code (Google Fonts) | Clean, professional, mono for code blocks |
| Deployment | Cloudflare Pages | Free, global CDN, no bandwidth limits |
| Forms | Formspree (free tier) | Zero backend contact form |

## Sections

- **Hero** — name, role, bio, CTA buttons, social links
- **About** — bio + key stats
- **Experience** — timeline: Comcast → AIROI → KU → Credit Suisse
- **Projects** — 5 inferred projects from work history
- **Skills** — 7 grouped skill categories
- **Education** — MS CS, University of Kansas
- **Interests** — 6 areas of professional interest
- **Contact** — social links + Formspree contact form

## Local Development

```bash
git clone https://github.com/vashok718/portfolio
cd portfolio
npm install
npm run dev
```

Open `http://localhost:4321` in your browser.

## Build

```bash
npm run build   # outputs to ./dist
npm run preview # locally preview the production build
```

## Customisation Checklist

Before deploying, update these placeholders:

- [ ] **Your name** — search for `Vashok` and replace with your full name
- [ ] **Email** — replace `your.email@example.com` in `Hero.astro` and `Contact.astro`
- [ ] **LinkedIn** — replace `linkedin.com/in/vashok718` in `Hero.astro` and `Contact.astro`
- [ ] **Formspree form ID** — replace `YOUR_FORM_ID` in `Contact.astro` (free at [formspree.io](https://formspree.io))
- [ ] **Resume PDF** — drop your `resume.pdf` into `public/assets/`
- [ ] **Cloudflare site URL** — update `site` in `astro.config.mjs`

## Deploy to Cloudflare Pages

### Option A — GitHub Integration (Recommended, zero CLI)

1. Push this repo to GitHub:
   ```bash
   git init
   git add .
   git commit -m "feat: initial portfolio"
   git branch -M main
   git remote add origin https://github.com/vashok718/portfolio.git
   git push -u origin main
   ```
2. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → **Pages** → **Create a project**
3. Connect your GitHub account and select the `portfolio` repository
4. Set build settings:
   | Setting | Value |
   |---------|-------|
   | Framework preset | Astro |
   | Build command | `npm run build` |
   | Build output directory | `dist` |
5. Click **Save and Deploy** — your site will be live at `portfolio-vashok718.pages.dev`

### Option B — Wrangler CLI

```bash
npm install -g wrangler
wrangler login
npm run build
wrangler pages deploy dist --project-name=portfolio
```

## Push to GitHub (fresh repo)

```bash
git init
git add .
git commit -m "feat: initial portfolio"
git branch -M main
git remote add origin https://github.com/vashok718/portfolio.git
git push -u origin main
```

> **Create the repo first** at [github.com/new](https://github.com/new) — name it `portfolio`, set it Public, do NOT initialise with README.

## Project Structure

```
portfolio/
├── public/
│   ├── assets/       ← Drop resume.pdf here
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   ├── Hero.astro
│   │   ├── About.astro
│   │   ├── Experience.astro
│   │   ├── Projects.astro
│   │   ├── Skills.astro
│   │   ├── Education.astro
│   │   ├── Interests.astro
│   │   └── Contact.astro
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │   └── index.astro
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── wrangler.toml
└── package.json
```

## License

MIT
