# Website Revision Plan — blairshevlin.github.io

_Last updated: 2026-07-04_

## Goal

Expand the current single-page site into a small **multi-page** academic website while keeping its clean, minimal look (serif uppercase name, generous whitespace, blue links). Add a shared top navigation bar and five sections: **Home, About, Research, Publications, Teaching**.

Design references: [shawnrhoadsphd.com](https://shawnrhoadsphd.com/) (nav + section rhythm), [yeelabneuro.com](https://yeelabneuro.com/) (multi-page structure), [gingjehli.com](https://www.gingjehli.com/).

## Decisions (confirmed with Blair)

| Question | Decision |
|---|---|
| Structure | **Separate pages** with a shared top nav bar |
| Visual design | **Keep the current look, add polish** (nav bar, section styling, social icons, hover states) |
| Title / affiliation | **Faculty — Instructor**, Dept. of Psychiatry, Icahn School of Medicine at Mount Sinai |
| Publications layout | **Peer-reviewed + Preprints** (two groups) |
| Mockups | **Clickable HTML preview** (in `/mockups/`) |

## Site architecture

```
index.html          → Home (landing)
about.html          → About + contact/links
research.html       → Research overview (3 themes)
publications.html   → Publications (peer-reviewed + preprints)
teaching.html       → Teaching philosophy + talks/workshops
assets/             → existing PDFs, images, CV (reused)
```

Shared top nav on every page: **Home · About · Research · Publications · Teaching**. Name/logo in nav links back to Home. Nav collapses gracefully on mobile (existing responsive breakpoint at 600px reused/extended).

Note: the live site is currently a standalone `index.html` (the old Jekyll `online-cv` template in `_includes/_layouts` is no longer the live design). Plan builds on the standalone-HTML approach for simplicity; no Jekyll rebuild required.

## Page-by-page content

### 1. Home (`index.html`)
- Name header (serif, uppercase — unchanged).
- Headshot (float right, as now).
- Two short intro paragraphs: who/where (Faculty/Instructor, CCP at Mount Sinai w/ Laura Berner; affiliated w/ Yale Computational Psychiatry Unit w/ Xiaosi Gu; PhD OSU Neuroeconomics Lab w/ Ian Krajbich) and the "How do people decide what to value?" framing.
- Quick-links line: CV · Google Scholar · GitHub · BlueSky · Email.
- Short "recent" pointer (optional): 1–2 highlighted papers or a "News" stub for later.

### 2. About (`about.html`)
- Slightly longer bio (background, training path, methods: computational modeling + fMRI + neurochemical recording).
- Contact block with icons/links:
  - Email: blair.shevlin@mssm.edu
  - BlueSky: [@bshev.bsky.social](https://bsky.app/profile/bshev.bsky.social)
  - Google Scholar: user J_t6LicAAAAJ
  - GitHub: github.com/blairshevlin
  - CV (PDF): assets/Shevlin_CV.pdf
- Optional: short "interests" / mentoring note (mentored 4 HS, 3 undergrad, 3 grad students; DEI + trainee-rep service).

### 3. Research (`research.html`)
Overview paragraph + three themed sections (drawn from Research Statement):
1. **Reward discriminability, attention & value representation** — DDM work showing high-value options are *more* discriminable (Shevlin et al., 2022, PNAS); attention (not noise) drives it (Shevlin & Krajbich, 2021); fMRI+eye-tracking dissociating input vs. integrator regions (Shevlin et al., 2026, eLife).
2. **Neurochemistry of reward & task context** — real-time dopamine/serotonin recordings during DBS for treatment-resistant depression; task-context specificity predicting clinical outcomes (Shevlin, Fu, et al., under revision, Nature); cross-species DDM work (mouse ASD model).
3. **Clinical translation across compulsive disorders** — emotion-induced attention shifts in bulimia nervosa (Shevlin et al., 2025, eLife); reward-discriminability imbalance hypothesis across binge-eating & substance-use; K01 / planned R01.

Each theme: 1 short paragraph, optionally with a representative figure/image placeholder and links to the key paper(s).

### 4. Publications (`publications.html`)
Two groups, reverse-chronological. Bold Blair's name; link each to PDF/DOI.

**Peer-reviewed**
- Overt visual attention modulates decision-related signals in ventral & dorsal medial PFC — *eLife* (2025)
- Computations underlying food choice among individuals with bulimia nervosa — *eLife* (2025)
- Restoring Weight and Brain Function… — *Biol. Psychiatry: CNNI* (2024)
- High-value decisions are fast and accurate… — *PNAS* (2022)
- Attention as a source of variability in decision-making… — *J. Math. Psychology* (2021)
- Past behavior and the decision to text while driving… — *Transportation Research Part F* (2019)

**Preprints & manuscripts under review / in prep**
- Dopamine & serotonin transients predict depressive symptom relief following DBS of human subcallosal cingulate cortex — *bioRxiv* (invited revision, Nature)
- The threat of synthetic respondents extends to clinical mental health screening — *PsyArXiv*
- A little goes a long way: fitting one-shot decisions with cognitive models — *PsyArXiv*
- Emotion prediction errors influence urges and behavior among individuals with binge eating — *in prep*
- Context-specificity and longitudinal stability of the effects of depressive symptoms on social decision-making — *in prep*

Optional footer link: "Full list on [Google Scholar]".

### 5. Teaching (`teaching.html`)
- **Teaching philosophy** (2–3 short paragraphs from Teaching Statement): every student can tackle complex problems; instructor as guide; active engagement, Socratic questioning, meeting learners where they are; transparency about own learning struggles; mentoring as guide-not-director.
- **Workshops & invited talks** (list with titles + venues + years):
  - *Using response times to improve cognitive models* — Yale School of Medicine (2025); Icahn School of Medicine (2025)
  - *Introduction to the diffusion decision model* — New York Computational Psychiatry Workshop (2024, 2025)
  - *Collecting Online Data in the Age of Large Language Models* — Icahn School of Medicine (2026); Yale School of Medicine (2026)
  - *Introduction to Decision-Making and the aDDM* — University of Gothenburg, Sweden (2021)
- **Teaching interests / course development** (optional): Neuroeconomics (undergrad); Computational Models of Choice; Advanced Computational Methods in Decision Research (grad).

## Visual / style notes
- Reuse current CSS tokens: system-serif name (Georgia), 16px body, `#0066cc` links, max-width ~1000px, headshot float-right.
- Add: sticky/simple top nav (uppercase, letter-spaced, current-page underline), thin section rule under `h2`, inline social icons (SVG, monochrome), link hover underline (already present).
- Keep everything single-file per page, no external JS frameworks. Mobile: nav wraps, headshot centers (existing 600px breakpoint).

## Build steps
1. ✅ Audit current site + extract statement content.
2. ✅ Confirm structure/design/title/publications decisions.
3. ✅ Write this plan.
4. **Build clickable HTML preview** in `/mockups/` (5 linked pages) — for feedback.
5. Iterate on preview per Blair's comments.
6. Promote approved pages to site root; keep old `index.html` as `index_old.html` backup.
7. Verify links (PDFs, Scholar, GitHub, BlueSky), mobile layout, and nav on every page.

## Open items / TODO
- Confirm exact journal year for the eLife attention/fMRI paper (2025 vs 2026 — statement cites 2026).
- Optional "News"/updates section — deferred unless wanted.
- Research-theme figures: reuse existing paper figures or leave text-only? (currently text-only in preview).
