# halfspaces — context

`halfspaces.co` — personal proof-of-work site. Live on Cloudflare Pages, GitHub repo `nigeleatworld/halfspaces`. Single `index.html`, personal-palette design system per `~/CLAUDE.md`.

## Site at a glance

Live since May 2026. Quarterly cadence. Audience: recruiters scanning for "can this person actually build" and peers scanning for "is this person thinking interestingly." Commercial artefacts (BCA, BrandVantage, Milieu) deliberately out of scope.

Five project threads live on the page: SpacePod, Mr. B, Budget Dashboard, Introspace, Bitpybit.

Palette: warm whites, parchment, linen, terracotta, forest, slate blue, ochre; a cool charcoal base (`--charcoal: #111B2E`, intentional); DM Sans + JetBrains Mono. Follows the `~/PALETTE.md` method (palette fits the task; WCAG AA contrast is the only hard rule). There is no "no navy" rule — that was a stale Claude-authored note, removed 2026-06-17.

## 2026-06-27 session (visitor-feedback round + project refresh + positioning copy)

Acted on feedback from a real first-time visitor, plus a project-accuracy audit and an article-driven positioning reframe. Commits `441f789`, `3145310`, `877b844`.
- **CV removed entirely** (both links gone, PDF untracked + de-whitelisted so it no longer deploys; local copy kept) — it was a non-tailored CV.
- **"Field notes" → "Build logs"** (the term was opaque to first-timers). Kept "proof-of-work" (deliberate voice).
- **All five project threads audited vs reality + refreshed:** Introspace `idea/concept/2025 → prototype/local/2026` (working Flask+SQLite MVP, was flagged as a mere "idea"); SpacePod `beta→live`, false `SQLite FTS5` chip → `Postgres + pgvector` +Stripe, `2025→2026`; Budget copy now names the investments view; all statuses aligned to `2026 / Status / medium`.
- **Positioning copy reframe (Codex-checkpointed):** hero lead now reads research as the *source* of judgment, not the pre-AI chapter; closing through-line retired the generic Einstein quote for Nigel's own thesis ("deciding what's worth building, then staying close enough to build it"). Driven by the Hudson/Lenny "inner game" frame (effort+knowledge commoditized; judgment + human layer is the edge). Removed orphaned `.closing cite` CSS.
- **Still open:** Claude's design fingerprint is recognisable (palette = biggest tell; Nigel okay with it for now). The Mr. B thread *understates* him (he now autonomously runs SpacePod + Introspace). The `building-halfspaces.md` writeup is still unpublished (a "Build logs" slot).

## 2026-06-16 session (SpacePod rebuild + Tier 1 polish + joint assessment)

- **SpacePod thread mock rebuilt** (commit `7396e03`) to match the live `spacepod.co` design, now the dark **"Quiet Orbit"** theme: near-black gradient panel, periwinkle `#7891F6` + gold `#D0A84B` + teal `#72A7B7` tokens, serif logo, real nav (Ask/Library), "From your podcast library" answer panel, source episode cards, the app's actual example-query chips. NOTE: the thread mocks are **coded HTML/CSS recreations, not screenshots** (Nigel's word "screenshots" = these recreations). SpacePod is now the only *dark* mock; the other four are light — deliberate (flagship) for now. Introspace deliberately left as-is.
- **Tier 1 polish shipped** (commit `93b5391`): added Open Graph + Twitter card + canonical + theme-color meta (link now unfurls a real preview card); new **favicon** `assets/favicon.svg` (half-space motif: warm charcoal tile, linen lanes, terracotta dot); new **1200×630 share card** `assets/og-image.png` (built in-palette via headless-Chrome screenshot of a temp HTML, then deleted the temp); whitelisted both new assets past the `assets/*` ignore rule; dropped stale "May 2026" from hero dateline → "Nigel Lin / Singapore"; gave `--slate-blue` a distinct `#3F6B85` (it had collapsed to the same `#53657D` as `--slate`, flattening that accent across ~16 uses).
- **CORRECTION — there is NO dark mode.** Earlier this session Claude wrongly asserted the site "supports light + dark via prefers-color-scheme" and labelled fixes "dark-mode-correct." Reality (Codex caught it): the two CSS var blocks are `.palette-field` (active, set on `<html>`) and `.palette-atelier` (unused) — both *light* palettes, switched by an HTML class, not the OS. No `@media (prefers-color-scheme: dark)` exists. The `color-mix`-on-theme-vars fixes are still good (palette-adaptive), just not "dark mode."
- **Joint website assessment** (Claude + Codex via `codex exec`, read-only). Open follow-ups NOT yet done:
  - ~~Navy palette decision~~ RESOLVED 2026-06-17: the PALETTE.md reset makes palette fit the task with AA contrast as the only universal, so the cool charcoal base is fine as an intentional choice. No "no navy" rule exists.
  - **"Build proof" rows (high-value content work):** add role / stack / status / live-or-private / journal-link to each project thread. Bigger session, not polish.
  - Lower: footer is bare (just "Top"); closing Einstein bicycle quote is generic vs Nigel's voice; orphaned local-only assets in `assets/` (artifact-*, mockups) sit unreferenced (already gitignored, so not deployed).

## "Field notes" — build-journal series (started 2026-06-13)

A **"Field notes" dropdown** now lives in the hero action row (`index.html`, native `<details class="fieldnotes">`), the index for a series of dated build journals. **Design/a11y pass shipped 2026-06-15/16** (commits `d483a08`, `c711678`, `2323ef4`): trigger typography matches sibling links (mono/uppercase/0.72rem); hover tint + panel shadow use `color-mix` on theme vars so they track the active palette class; semantic `<ul>/<li>` (not `role="menu"`); "soon" rows use `--ash`, not opacity; mobile panel goes static full-width; small JS added for click-outside + Esc dismiss. (An earlier "no JS" note here was a description, not a constraint.) Fixed a z-index bleed-through by giving `.hero-copy` `z-index:2` (its `.reveal` transform was trapping the panel's z-index under the "high agency…" tagline). **Alignment gotcha (resolved):** the summary kept looking un-aligned with its row-mates; root cause was the `font:` shorthand resetting `line-height` to `normal` while sibling `.text-link`s inherit body `line-height:1.5` — making the summary box shorter so its underline sat at a different height in the centre-aligned row. Fix: set `line-height:1.5` on the summary explicitly. First journal PUBLISHED:

- **`building-chatpulse.html`** — "Building chatpulse," the build journal for the chatpulse project (see `~/projects/chatpulse`). Live at `halfspaces.co/building-chatpulse`. Standalone self-contained HTML page in the site palette (DM Sans / JetBrains Mono). Dated journal (7 May–12 Jun 2026), Nigel's voice. **Discretion rules baked in: NO source/author/publication names anywhere** (chatpulse ingests paid newsletters; sources stay anonymous, framed as "a handful of paid investing newsletters" etc.). Honest-credit framing: Claude did the building + its fumbles, Nigel directed/decided/waited.
- **Pattern for the rest of the series:** each journal is a standalone responsive HTML page in the site palette; diagrams are **responsive HTML (flexbox `.pipe`/`.cols`/`.stage`/`.arrow`, fluid `clamp()` text)**, NOT fixed SVG — they reflow row→vertical-stack and stay crisp on phones (the SVG version shrank text + needed horizontal scroll; rebuilt). Add each new one to the dropdown's `.fn-panel`.
- Dropdown items marked **"soon"** (no link yet): halfspaces, SpacePod, Mr. B, Introspace, Bitpybit. `building-halfspaces.md` exists as markdown (below) but isn't yet an HTML page; convert + link it to fill its "soon" slot.

## In-flight — building-halfspaces writeup (2026-05-23; now a "Field notes" candidate)

**Writeup for the site — `building-halfspaces.md` (~1,300 words).**

- Title: **"Building halfspaces"**
- Placement: NOW its slot in the **Field notes dropdown** (currently "soon"). Convert the markdown to a standalone HTML page (same template as `building-chatpulse.html`), then flip its dropdown entry to a live link.
- Status: drafted and revised. **Not yet published** (still markdown).

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
4. **Convert markdown to styled HTML** in the site palette (DM Sans body, JetBrains Mono labels).
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
