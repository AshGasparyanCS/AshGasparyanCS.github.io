# Personal Portfolio

A single-file, zero-build personal portfolio for a new-grad software engineer.
Pure HTML/CSS/JS — no framework, no build step, no dependencies (fonts load from
Google Fonts via CDN). Open it, edit it, ship it.

## Sections
- **Hero** — name, tagline, availability/status chips, CTAs
- **About** — bio + a "quick stats" panel
- **Skills** — grouped by Languages / Frameworks / Tools
- **Projects** — data-driven cards (title, description, tech stack, code/demo links, status badge)
- **Contact** — email, GitHub, LinkedIn

Design: a "service-monitoring console" identity — dark panels, a "healthy" teal
accent, monospace for data, pulsing status dots, scroll-reveal on each block.
Fully responsive, keyboard-focusable, and respects `prefers-reduced-motion`.

## Run it locally
No build needed. Either:

    # just open the file
    open index.html            # macOS
    start index.html           # Windows (PowerShell)

Or serve it (recommended, avoids any file:// quirks):

    python -m http.server 8080
    # then visit http://localhost:8080

## Customize
Everything lives in `index.html`.

1. **Your info** — find/replace these placeholders:
   - `you@example.com`  → your email (appears in the contact button + mailto link)
   - `your-username`    → your GitHub username
   - `your-handle`      → your LinkedIn handle
   - `Ash` / `ash.dev`  → your name / brand
2. **Projects** — edit the `PROJECTS` array near the bottom of the file.
   Each entry: `{ title, status, desc, tags, repo, demo }`.
   - `status`: `"wip"` (shows "in progress") or `"live"` (shows "live")
   - `repo` / `demo`: set to a URL, or `null` to hide that link
   As you ship each project, paste its GitHub URL into `repo`, add a `demo`
   URL if you have one, and flip `status` to `"live"`.
3. **Colors** — all in the `:root` block at the top of the `<style>` tag.
   Change `--up` to re-skin the whole accent.

## Deploy
Because it's static, any of these work in a couple of minutes:

### GitHub Pages
    git init && git add . && git commit -m "portfolio"
    git branch -M main
    git remote add origin https://github.com/your-username/portfolio.git
    git push -u origin main
Then: repo → Settings → Pages → Source = `main` / root.
Live at `https://your-username.github.io/portfolio/`.

### Netlify
Drag the folder onto https://app.netlify.com/drop — done. Or connect the repo;
no build command needed, publish directory = `/`.

### Vercel
    npm i -g vercel
    vercel
Accept the defaults (no framework, no build command). It auto-deploys on push.

## Notes
- If you later want a multi-file React/Vite version (separate components,
  `data.js`, etc.), the structure maps 1:1 — Hero/About/Skills/Projects/Contact
  each become a component and `PROJECTS` becomes the data module.
