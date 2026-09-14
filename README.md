# hamedkhosravi99.github.io

Personal academic website — <https://hamedkhosravi99.github.io>

Plain HTML + CSS. No Jekyll, no build step, no dependencies. Edit the files, commit, push;
GitHub Pages serves the result within a minute or so.

## Pages

| Path | What it is |
|---|---|
| `index.html` | **Home** — identity header, About, Research Interests, Selected Publications (5), Experience, Education. The page for a recruiter or hiring manager. |
| `projects.html` | Research projects, Current / Past, each with a figure and its papers |
| `publications.html` | Every publication |
| `news.html` | News, back to 2022 |
| `presentations.html` | Talks and posters |
| `awards.html` | Honors & Awards, then Academic Service |
| `style.css` | All the styling (light + dark, responsive, print) |
| `assets/profile.jpg` | Headshot |
| `assets/projects/` | Project figures |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |

Every page starts with the same top bar (`<header class="topbar">`). **It is repeated
verbatim in all six files** — if you add or rename a page, edit the bar in every file.
The link with `class="active"` is the current page.

There is deliberately no CV on this site.

## Editing

Each page's content sits in plainly-labelled sections. To add an item, copy the block
above it and change the text:

- **News** (`news.html`): `<li><span class="date">Sep 2026</span><span class="item">…</span></li>`
- **Publication** (`publications.html`): copy one `<li>` inside `<ol class="pubs">`; the
  `tags` span holds the Paper/Code buttons. To feature it on the home page, also copy it
  into the `<ol class="pubs">` in `index.html` and drop the oldest of the five.
- **Presentation / award** (`presentations.html`, `awards.html`): copy one `<li>` of the
  timeline; keep the list in reverse-chronological order.
- **Project** (`projects.html`): copy an `<article class="project">`. Figures go in
  `assets/projects/`; use the paper's own figure, trimmed of margins, ~1400px wide.

## Preview locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Settings → Pages → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)`.

**When you change `style.css`, also bump the `?v=` on the stylesheet link in every
page** (e.g. `style.css?v=20260915a` → today's date). GitHub Pages caches files for
10 minutes; without the bump, a visitor can receive new HTML with a stale cached
stylesheet and see an unstyled page until the cache expires.

The same applies to images: **if you replace an image's content, give it a new
filename** (and update the `src`). A browser that cached `assets/projects/foo.jpg`
will keep showing the old picture for 10 minutes if the name doesn't change.
