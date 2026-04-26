# Data Analysis with AI — book

A **standalone Quarto book** for late-undergraduate and first-year postgraduate students in economics, finance, business, analytics, and PPE who already know some Python and some econometrics, and now want to make AI a daily collaborator without losing their judgement.

This is not a companion website. It is a book. The course at [github.com/gabors-data-analysis/da-w-ai](https://github.com/gabors-data-analysis/da-w-ai) is the live-class form of the same material; this repo is the linear-narrative book derived from it. The two evolve in parallel.

- **Edition:** Spring 2026, 26 April 2026
- **Models referenced:** Claude Opus 4.7, Claude Sonnet 4.6, Claude Haiku 4.5, ChatGPT 5.5
- **Companion textbook:** [Békés & Kézdi, *Data Analysis for Business, Economics, and Policy*](https://gabors-data-analysis.com/getting-started) (Cambridge UP, 2021) — read alongside or before
- **License:** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
- **Author:** [Gábor Békés](https://sites.google.com/site/bekesg/), CEU
- **Live site:** https://gabors-data-analysis.com/da-w-ai-book/

## Who the book is for

- Second- or third-year undergraduates in economics, finance, business, analytics, or PPE.
- First-year MA / MSc students in any of the above.
- Readers who have done one solid data-analysis or econometrics course (Békés–Kézdi or equivalent) and have working Python.
- Readers comfortable enough with a chat AI to have used it casually, but who have not yet used it inside an analytical workflow they would defend.

We do not assume Git, GitHub, terminal use, an IDE, or API experience. **Part 0** covers all of that.

## What's in the book

```
da-w-ai-book/
├── _quarto.yml          # book project + TOC
├── index.qmd            # Preface (4–5 page standalone essay)
├── how-to-use.qmd       # How to read it; chapter shape; book + labs split
├── versions.qmd         # Edition + model snapshot (refresh each spring)
├── chapter-template.qmd # The chapter skeleton specification
├── linear-plan.qmd      # Editorial rationale + open follow-ups
├── custom.scss          # Styling
├── images/              # Legacy figures from the live course; being phased out
├── chapters/            # Numbered chapters across nine parts + reference + appendix
├── labs/                # Stripped-down labs that mirror the original assignments
└── .github/workflows/
    └── publish.yml      # render + deploy to gh-pages on every push to main
```

The book has **eight narrative parts plus front and back matter**:

| Part | Focus |
|---|---|
| Front matter | Preface, How to use, Edition + model snapshot |
| **Part 0** | Set up your tools — git, GitHub, Python, AI account |
| **Part I** | What an LLM is, and what it isn't |
| **Part II** | Working with AI in chat |
| **Part III** | From chat to CLI — agentic workflows |
| **Part IV** | Text as data |
| **Part V** | AI in empirical research — controls, IV |
| **Part VI** | APIs and automation |
| **Part VII** | Capstone — Manager Impact in Football |
| **Part VIII** | Labs — work on your own |
| **Part IX** | Working honestly — academic integrity, cost and budget |
| Reference | Case studies, where to go from here, the linear plan |
| Appendix | Rights, acknowledgements, thanks |

Many chapters are currently inlined source content from the live course, slated for rewrite to the chapter template. Part 0, parts of Part I, and Part IX are placeholder stubs awaiting their first draft.

## Editorial decisions (locked for Spring 2026)

- **Standalone book**, not a companion website. Each chapter is self-contained on the page.
- **No pictures by default.** Diagrams only when prose cannot do the job; no screenshots.
- **Python only.** Principles transfer to R, Stata, Julia; the code does not.
- **Claude Code as the CLI agent.** Cursor / Codex / Aider get one-paragraph mentions.
- **Web-first delivery, single edition per spring.** Print is a future editor's job from a frozen snapshot.
- **Variable chapter length.** 1–2 pages for a single idea; 4–5 sparingly for an end-to-end walkthrough. No artificial uniformity.
- **One chapter template, two flavours** (Learn / Practice). Same skeleton; weights move. See [chapter-template.qmd](chapter-template.qmd).
- **Brief econometrics + textbook redirect.** Methods are pointed at Békés–Kézdi rather than re-derived.

Rationale lives in [linear-plan.qmd](linear-plan.qmd).

## Build locally

```bash
quarto preview        # live preview, HTML
quarto render         # full HTML render → _book/
```

Requires [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4 and Python (only if you plan to execute code chunks). RStudio / VS Code / a plain terminal all work.

## Deploy

`.github/workflows/publish.yml` renders the book on every push to `main` and publishes to the `gh-pages` branch via [peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages). The site is served at https://gabors-data-analysis.com/da-w-ai-book/ via the org's Pages custom domain.

## Open follow-ups

Tracked in [linear-plan.qmd](linear-plan.qmd):

1. Per-chapter rewrite via the writing skill (the chapter-template specification).
2. Internal-link audit (course-website paths still appear in inlined content).
3. Strip remaining R snippets — Python only.
4. Drop the `images/` folder once references are gone.
5. Fill the placeholder chapters in Parts 0, I, and IX.
6. Final image-free pass.

## Contributing

Open an issue or PR against this repo. For typo-level errata, a PR is fastest. For structural suggestions or curriculum debates, an issue is better.

## Acknowledgements

See [`chapters/A1-rights-thanks.qmd`](chapters/A1-rights-thanks.qmd).
