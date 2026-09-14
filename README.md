# hamedkhosravi99.github.io

Personal academic website — <https://hamedkhosravi99.github.io>

Plain HTML + CSS. No Jekyll, no build step, no dependencies. Edit the files, commit, push;
GitHub Pages serves the result within a minute or so.

## Files

| Path | What it is |
|---|---|
| `index.html` | All the content — every section is a plainly-labelled `<section>` |
| `style.css` | All the styling (light + dark, responsive, print) |
| `assets/profile.jpg` | Your headshot. **Not yet added** — see below |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |

## One thing to add

**Headshot** → save a square photo (≈600×600) as `assets/profile.jpg`.
Until then the site shows a circular "HK" monogram, which degrades gracefully.

There is deliberately no CV on this site.

## Editing

Everything lives in `index.html` under a commented banner:

```
<!-- ---------- NEWS ---------- -->
```

To add a news item, copy the line above it and change the text:

```html
<li><span class="date">2026</span> Your news here.</li>
```

To add a publication, copy one `<li>` block inside `<ol class="pubs">`. The `tags` span
holds the Paper/Code/Slides buttons — add, remove, or rename them freely.

A **Teaching** section is written but commented out near the bottom of `index.html`,
because its entries are placeholders. Fill in the real courses and delete the two
comment markers around it to publish.

## Preview locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Settings → Pages → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)`.

**When you change `style.css`, also bump the `?v=` on the stylesheet link in
`index.html`** (e.g. `style.css?v=20260914` → today's date). GitHub Pages caches
files for 10 minutes; without the bump, a visitor can receive the new HTML with a
stale cached stylesheet and see an unstyled page until the cache expires.
