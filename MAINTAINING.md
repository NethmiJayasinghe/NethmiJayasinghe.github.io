# Maintaining this site

Personal academic site: a homepage (`index.html`) + one project page per paper.
Plain HTML/CSS/JS — no build step, no dependencies. Light/dark mode.

## Structure
```
index.html                              # homepage: bio, research themes, publications, experience, education, skills
assets/project.css                      # shared style for project pages (+ dark mode)
assets/figs/                            # figures for project pages
cv/Nethmi_Jayasinghe_CV.pdf             # CV linked from the homepage
papers/                                 # paper PDFs and per-paper assets
projects/cerebellar-residual.html       # ICML 2026 project page
projects/memtransistor-attention.html   # IEEE EDL 2024 project page
```

## Deploy (GitHub Pages)
Files live at the repo root of `NethmiJayasinghe.github.io` and serve automatically
from the `main` branch (Settings → Pages → Deploy from branch → `main` / root).
Changes go live ~30–60s after a push.

Local preview: `python3 -m http.server 8000` → http://localhost:8000

## Add a new paper
1. **Homepage:** add an entry to the `publications` array in `index.html`
   (set `status`, `page`, and `authors` with `"__ME__"` for your name).
2. **Project page:** copy `projects/cerebellar-residual.html`, update the
   title / authors / abstract / results / BibTeX, save under `projects/<slug>.html`.

The homepage shows a discreet "+N manuscripts under review" line
(`underReviewCount` in `index.html`) — update or remove as needed.

## Conventions
- Use hyphens (`-`), not em-dashes (`—`).
- Bold = best, underline = second-best in results tables; highlight the "Ours" row with `class="ours"`.
