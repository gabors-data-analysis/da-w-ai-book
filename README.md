# Data Analysis with AI — book

A **Quarto book** for social science students who already know some Python and some econometrics, and now want to make AI a daily collaborator without losing their judgement.

This is the book companion to the open course **Doing Data Analysis with AI**, taught at CEU in Vienna. The course-website version lives at [github.com/gabors-data-analysis/da-w-ai](https://github.com/gabors-data-analysis/da-w-ai); this repo is the linear-narrative book derived from the same material.

- **Edition:** Spring 2026, 26 April 2026
- **Models referenced:** Claude Opus 4.7, Claude Sonnet 4.6, Claude Haiku 4.5, ChatGPT 5.5
- **License:** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
- **Author:** [Gábor Békés](https://sites.google.com/site/bekesg/), CEU

## What's here

```
da-w-ai-book/
├── _quarto.yml          # book project: TOC, parts, HTML format
├── index.qmd            # Preface
├── how-to-use.qmd       # How to read the book; book/labs split
├── versions.qmd         # Edition + model snapshot (refresh each spring)
├── linear-plan.qmd      # Editorial rationale + week→chapter mapping
├── custom.scss          # Site styling (Viridis palette, hero blocks, week cards)
├── images/              # Figures referenced by chapters
├── chapters/            # 35 chapter files in 7 narrative parts
│   ├── 01-ai-for-coding.qmd … 34-capstone-did.qmd
│   ├── 90-case-studies.qmd
│   ├── 91-beyond.qmd
│   └── A1-rights-thanks.qmd
├── labs/                # 10 stripped-down hands-on labs (no Lab 9 in source)
│   ├── index.qmd
│   └── lab-01.qmd … lab-10.qmd
└── .github/workflows/
    └── publish.yml      # render + deploy to gh-pages on every push to main
```

The book is structured in eight parts plus a Reference section and an appendix. See [`_quarto.yml`](_quarto.yml) for the full TOC and [`linear-plan.qmd`](linear-plan.qmd) for the editorial rationale.

## Build locally

```bash
quarto preview        # live preview, HTML
quarto render         # full HTML render → _book/
```

Requires [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4 and Python (only if you plan to execute code chunks).

## Deploy

`.github/workflows/publish.yml` renders the book on every push to `main` and publishes the result to the `gh-pages` branch via [peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages).

**One-time GitHub setup after the first push lands:**

1. Repo → **Settings** → **Pages**.
2. Under **Build and deployment** → **Source**, choose **Deploy from a branch**.
3. **Branch:** `gh-pages` · **Folder:** `/ (root)` → **Save**.
4. The book will go live at `https://gabors-data-analysis.github.io/da-w-ai-book/` within a minute or two.

The first push to `main` triggers the first render and creates the `gh-pages` branch automatically.

## Editorial decisions (locked for Spring 2026)

- **Python only.** No R, no side-by-side. Principles transfer; the code in this edition does not.
- **Claude Code as the CLI agent.** Cursor / Codex / Aider get one-paragraph mentions where they differ usefully.
- **Web-first.** A print edition is the print editor's problem from a frozen snapshot.
- **Yearly spring edition.** Model snapshot in [`versions.qmd`](versions.qmd). Errata between editions go in the issue tracker.
- **Econometrics: brief + redirect.** Where the book brushes against DiD/IV/etc., we cover the *workflow* and point readers at [*Data Analysis for Business, Economics, and Policy* (Békés & Kézdi, 2021)](https://gabors-data-analysis.com/getting-started) for the method.
- **Many short chapters** over few long ones. Prefer splitting over merging as content fleshes out.

See [`linear-plan.qmd`](linear-plan.qmd) for the rationale behind each.

## Known issues in this draft

These are open follow-ups, not blockers for the first deploy:

1. **Internal links still point to the website.** Many inlined chapter sections reference the course's URL structure (`/da-knowledge/which-ai.html`, `../week08/index.qmd`, `/case-studies/...`). In the book they should resolve to chapter anchors. Needs a one-pass `sed` once the structure stabilises.
2. **Hero blocks at chapter starts.** The `::: {.hero-section}` divs inherited from the course pages are visually heavy at the top of every chapter. Trim or restyle in a later pass.
3. **Doubled chapter heading on some pages.** A chapter with both a wrapper `# Title` and an inlined `# Title` from the source can render two H1s. Visible on a few chapters; cosmetic.
4. **Image paths assume `images/` at repo root** — handled in this repo (we copy `da-w-ai/images/`). If image filenames change in the source course, they need to be re-synced here.
5. **Lab 9 is intentionally absent** — there is no `assignment_09.qmd` in the source.
6. **Some inlined sources still mention R.** Python-only is the editorial intent; the next pass strips the R snippets that survived the migration.

## Relationship to the course repo

- **Source of truth for the website:** [`gabors-data-analysis/da-w-ai`](https://github.com/gabors-data-analysis/da-w-ai). The course's weekly modules, knowledge-base pages, assignments, and case studies all live there.
- **Source of truth for the book:** this repo.
- **Sync rhythm:** annual, in spring. Each spring, walk through the course material, port what's changed into the book, refresh the model snapshot in [`versions.qmd`](versions.qmd), tag a release.

## Contributing

Open an issue or PR. For typo-level errata, a PR is fastest. For structural suggestions or curriculum debates, an issue is better.

## Acknowledgements

See [`chapters/A1-rights-thanks.qmd`](chapters/A1-rights-thanks.qmd) for the full acknowledgements.
