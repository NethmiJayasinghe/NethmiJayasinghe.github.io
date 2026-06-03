# Nethmi Jayasinghe — personal website

Modern academic site: a homepage (`index.html`) + one Nerfies-style **project page per paper**.
Plain HTML/CSS/JS — no build step, no dependencies. Has light/dark mode.

## Structure
```
index.html                              # homepage: bio, research themes, publications
assets/project.css                      # shared style for project pages (+ dark mode)
assets/figs/                            # drop paper figures here
papers/                                 # paper PDFs
projects/cerebellar-residual.html       # ICML 2026 project page
projects/memtransistor-attention.html   # IEEE EDL 2024 project page
```

## Deploy to GitHub Pages
1. Create a repo named **`<your-username>.github.io`** (for the root site) — or any repo if you want a `/repo` path.
2. Copy the contents of this `site/` folder into the repo root.
3. Commit & push to the `main` branch.
4. In the repo: **Settings → Pages → Source: Deploy from branch → `main` / `root`**.
5. Live at `https://<your-username>.github.io/` in ~1 minute.

Local preview: `cd site && python3 -m http.server 8000` → open http://localhost:8000

## Fill in before going live
- **Profile links** in `index.html` (hero section): replace `REPLACE_SCHOLAR_URL`,
  `REPLACE_GITHUB_URL`, `REPLACE_LINKEDIN_URL` with your real URLs.
- **Figures**: each project page has a dashed placeholder box. Export the figure from the
  PDF to `assets/figs/...png`, then replace the `<div class="fig-placeholder">…</div>`
  with `<img src="../assets/figs/yourfig.png" alt="...">`.

## Add the 3 in-review papers later
Two steps each:
1. **Homepage:** add an entry to the `publications` array in `index.html`
   (set `status` to one of `published` / `accepted` — add a `review` badge if you want,
   set `page:` to the new project page, list `authors` with `"__ME__"` for your name).
2. **Project page:** copy `projects/cerebellar-residual.html`, change the title/authors/
   abstract/BibTeX, save under `projects/<slug>.html`.

The homepage currently shows a discreet "+3 manuscripts under review" line
(`underReviewCount` in `index.html`) with no titles/venues — change or delete as you like.
