# Personal portfolio

My personal portfolio site. One file, no build step, no framework, no dependencies (the fonts load from Google Fonts over a CDN). Just open `index.html`, edit it, ship it.

Live at https://AshGasparyanCS.github.io

## Sections

- **Hero**: name, tagline, availability/status chips, call-to-action buttons.
- **About**: short bio plus a quick-stats panel.
- **Skills**: grouped into Languages / Frameworks / Tools.
- **Projects**: data-driven cards (title, description, tech stack, code/demo links, status badge).
- **Contact**: email, GitHub, LinkedIn.

The look is a "service-monitoring console": dark panels, an orange accent, monospace for anything data-like, pulsing status dots, and a scroll-reveal on each block. It's fully responsive, keyboard-focusable, and respects `prefers-reduced-motion`.

## Run it locally

No build needed. Either open the file directly:

    start index.html           # Windows (PowerShell)
    open index.html            # macOS

or serve it (nicer, avoids any file:// quirks):

    python -m http.server 8080
    # then visit http://localhost:8080

## Editing it

Everything lives in `index.html`.

- **Projects** are in the `PROJECTS` array near the bottom. Each entry is `{ title, status, desc, tags, repo, demo }`. `status` is `"wip"` (shows "in progress") or `"live"`. `repo`/`demo` take a URL, or `null` to hide that link. As I finish a project I push its repo, drop the URL into `repo`, and flip `status` to `"live"`.
- **Colors** are all in the `:root` block at the top of the `<style>` tag. Changing `--up` re-skins the whole accent in one line.

## Deploy

It's static, so GitHub Pages hosts it for free. The repo is named `AshGasparyanCS.github.io`, so it serves from the root automatically:

    git add .
    git commit -m "update site"
    git push

Then it's live at https://AshGasparyanCS.github.io within a minute. Netlify or Vercel would also work if I ever wanted them (drag the folder onto Netlify drop, or run `vercel` with the default no-build settings).

## Notes

If I ever want a multi-file React/Vite version, the structure maps over cleanly: Hero/About/Skills/Projects/Contact each become a component, and `PROJECTS` becomes a data module.
