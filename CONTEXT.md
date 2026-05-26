# halfspaces — context

`halfspaces.co` — personal proof-of-work site. Live on Cloudflare Pages, GitHub repo `nigeleatworld/halfspaces`. Single `index.html`, personal-palette design system per `~/Desktop/claude-code-playground/CLAUDE.md`.

## Site at a glance

Live since May 2026. Quarterly cadence. Audience: recruiters scanning for "can this person actually build" and peers scanning for "is this person thinking interestingly." Commercial artefacts (BCA, BrandVantage, Milieu) deliberately out of scope.

Five project threads live on the page: SpacePod, Mr. B, Budget Dashboard, Introspace, Bitpybit.

Brand spec: warm whites, parchment, linen, terracotta, forest, slate blue, ochre. No navy, no pure white. DM Sans + JetBrains Mono.

## In-flight (2026-05-23)

**Writeup for the site — `building-halfspaces.md` (~1,300 words).**

- Title: **"Building halfspaces"**
- Placement: subtle about/history page on `halfspaces.co`. Nigel's framing: "nothing loud, but there — FOR NOW."
- Status: drafted and revised. **Not yet published.**

**Irreducibly-Nigel anchors in the draft (added to puncture AI-essay smoothness):**

1. Opening — wardrobe line: white/grey tees, five comfortable-fitting yoga pants from the same brand, oversized retro jerseys → "I'm the last person who'd know what tasteful design looks like."
2. *Hero was the hardest part* — Ya Kun morning anchor: "Most of the work happened mornings at Ya Kun, after dropping Brennan at infant care; laptop on the table, kopi c siu dai peng in a takeaway cup, and back to the file."
3. *Design is mostly saying "not that"* (photo paragraph) — "one version had my face planted huge on the hero, which I will not be sharing."
4. *Shipping* — Amanda anchor: "Before launch, no one had seen the site. Amanda had been pleased with the name from early on, which helped; everything else I'd kept to myself."

**De-AI-ification fixes applied:** broke cascading X-Y-Z lists, added two mid-thought self-corrections (the dot strip "or mid-process; I keep calling it late"; the colour-or-spacing "they ran in parallel"), softened the closing aphorism (past tense, no chiasmus), varied the "didn't know" repetition in *What AI did not do*, dropped the CTA paragraph entirely, collapsed the *Five threads, one structure* section into one paragraph in *Design is mostly saying "not that"*.

Full checklist of cheap fixes for future Nigel-voice writing: see `feedback_writing_de_ai.md` (auto-memory).

**Older long-form draft kept at `website-building-article-draft.md`** (~7,600 words, 18 May). Will not be published; reference only.

## Open items to publish the writeup

1. **Locate the halfspaces git repo on this machine** (or confirm it's only on the work Macbook Pro).
2. **Verify push auth** from whichever machine. SSH key or `gh` CLI logged in to `nigeleatworld/halfspaces`.
3. **Decide HTML integration approach.** Options: (a) inject a styled HTML section at the bottom of `index.html` with a small footer link, (b) add a separate `/about.html` or `/building.html` page and slip a small link into the existing nav row. Nigel said "subtle" and "FOR NOW."
4. **Convert markdown to styled HTML** in the personal palette (DM Sans body, JetBrains Mono labels, no navy).
5. **Stage commit and let Nigel diff before push.** Default posture is confirm-before-push for public URLs (per system rules on risky actions).

## Files

- `index.html` — the live site
- `index.original.html` — pre-rewrite backup (13 May)
- `building-halfspaces.md` — current canonical writeup
- `website-building-article-draft.md` — long-form earlier draft (reference only)
- `DESIGN.md` — site design brief (older, pre-rewrite)
- `handover-from-claude.md` — 13 May handover memo from prior Claude session
- `assets/` — artefact PNGs (BCA and Brandvantage unused on purpose)

## How to resume

1. Open `building-halfspaces.md` to see the current writeup.
2. If publishing, work through the open items list above. Locate repo first.
3. If iterating on the writeup further, scan against `feedback_writing_de_ai.md` to avoid re-introducing AI smell.
