> **This is a copy, not the source of truth.** The real file lives at
> `docs/handoff/HOOK-MODULES.md` in `wtdickens/health-dashboard` (private, code repo — the
> research/writing team doesn't have access there yet). Copied here on 2026-09-24, at commit
> `db9f1b7`, so it's readable without code-repo access. If the two ever disagree, the
> health-dashboard original is authoritative, not this copy.
>
> This copy should be deleted once health-dashboard moves to the Visualize-Policy account and goes
> public — at that point everyone can just read the original directly instead of a snapshot that
> can go stale.

---

# What already exists for the hook modules and the glossary

**What this covers:** an inventory of data, functions, and components already in the repo that the
volunteer teams working on the two "hook" modules and the three-layer glossary expansion can build
on directly, so nobody re-derives something that's already built. Written for volunteers who are
new to the codebase — assume no prior context.

**What it does not cover:** how to run the data build (`DATA-PIPELINE.md`), the Medicaid eligibility
table's completeness (`MEDICAID-TABLE.md`), or the open modeling decisions for the core simulator
(`MODEL-ROADMAP.md`). This document is about what a UI/content team can reuse today, not about the
unbuilt mixed-logit choice model.

---

## Hook module 1 — "what do people near you pay, and where do they get coverage"

**Already built, ready to use:**

- `data/processed/combined/county_coverage.csv` — coverage-type shares and the SAHIE uninsured rate,
  one row per county. Built by `site_data_prep/aggregate_by_county.py`.
- `site_code/src/data/counties.json` — the site's already-built county-level JSON, live on the map
  today.
- `site_code/src/components/choropleth.js` — the map component: click-to-select, hover tooltip,
  custom tooltip text via `titleFn`. This is very likely the right building block for a
  "click your county" interaction rather than a new map from scratch.
- State-level marketplace benchmark premiums: `normalize_benchmark_premium()` in
  `import_data/marketplace/kff_normalizers.py`, sourced from KFF's Custom State Report. This is
  actual dollar-figure premium data, not just coverage shares.

**Not yet built:** a *county-level* premium figure. What exists is state-level (KFF doesn't publish
finer than that) — a "how much do people in your county pay" framing will need to either use the
state figure with an honest caveat, or find/build a county-level premium proxy. Worth deciding which
before writing copy that implies a precision the data doesn't have.

---

## Hook module 2 — "do you qualify for marketplace subsidies, CHIP, Medicaid, or Medicare"

**This is the one with the most already built — read this before scoping the issue.**

- `modeling/cost/engine.py::estimate_subsidy()` is a complete, working function. Give it annual
  income, household size, and a benchmark monthly premium, and it returns: whether the household is
  premium-tax-credit eligible, the applicable percentage of income, the estimated monthly credit,
  the net premium after the credit, the CSR (cost-sharing reduction) tier if any, **and a
  `medicaid_likely` flag** (income under ~138% of the federal poverty level, the expansion-state
  Medicaid threshold). This already covers most of the marketplace-subsidy half of this hook, and a
  first pass at the Medicaid half.
- `modeling/cost/constants.py` has the FPL tables, the applicable-percentage schedule, the CSR bands,
  and the ACA age-rating curve the engine reads from — the actual current numbers, not placeholders.
- `data/processed/medicaid/medicaid_eligibility_2025.csv` — state-by-eligibility-group income
  ceilings (612 rows: 51 states × 12 groups), covering the finer Medicaid/CHIP categories
  `estimate_subsidy()`'s single 138% cutoff doesn't capture — pregnant women, children, parents, and
  separate-CHIP thresholds all vary by state and are in this table.

**Not yet built:**
- Nothing currently *reads* `medicaid_eligibility_2025.csv` — no Python function turns "household
  characteristics + this table" into a yes/no per program the way `estimate_subsidy()` does for the
  marketplace. That's the reserved, empty `modeling/eligibility/` package (issue #4 in the roadmap,
  not started).
- CHIP-specific logic beyond the raw income ceilings — no premium/cost-sharing calculation for CHIP
  exists yet (see `MEDICAID-TABLE.md` section 5 on how thin that data still is).
- Medicare eligibility isn't in any of this — per `MODEL-ROADMAP.md` 2.5 it's being kept out of the
  main simulator as a separate deterministic model. It's also the simplest of the four programs
  (age 65+, plus some disability/ESRD categorical paths), so it's probably fine for this hook to
  encode it directly rather than wait on anything.

**Why this matters for how the issue gets scoped:** a "design an eligibility checker" issue handed
to the research/writing group should be framed as *UX and content design on top of logic that will
eventually call the same rules as the core model* — not as "figure out the eligibility rules and
build the checker," which risks a second, independently-invented interpretation of "who qualifies
for Medicaid in Ohio" that quietly diverges from `medicaid_eligibility_2025.csv` and whatever
`modeling/eligibility/` ends up being. Whoever leads this hook should be coordinating with whoever
picks up the eligibility-model coding work, not working from it in isolation.

---

## The three-layer glossary

The three layers as described: (1) a one-line rollover tooltip, (2) a click-through paragraph-level
box, (3) a hyperlink from the bottom of that box to a page-length deep dive (history, provisions,
eligibility rules, etc.).

**Already built — layers 1 and 2's *content* fields, not yet their intended interaction:**

- `site_code/src/data/concepts/concepts.json` — the registry. Each entry already has `id`, `term`,
  `short` (one line), `body` (an array of paragraphs), and `sources`. `short` and `body` map
  directly onto layers 1 and 2's content.
- `site_code/src/components/concept.js` — `conceptRef()` (inline link), `conceptBox()` (an expandable
  `<details>` box embeddable on any page), `conceptStrip()` (renders several boxes at once), and
  `glossary()` (the full `/concepts/` page).

**Not yet built, and this is a coding task, not a content one — flag this before handing the issue
to a content-only team:**

- Today, `short` is always visible as plain text next to the term (inside the `<summary>`), and
  clicking the `<details>` element reveals `body` — there's no hover-triggered popup anywhere in
  this component. Layer 1 as described (rollover-triggered) doesn't exist as an interaction yet.
  This site already has an established hover-on-pointer/tap-on-touch convention used elsewhere
  (see `site_code/ARCHITECTURE.md`, "Design principles") — layer 1 should very likely reuse that
  same pattern rather than invent a new one.
- There's no third field or page type for a page-length deep dive. The closest existing pattern in
  the codebase is `/history/index.md`'s slide-deck-style long-form layout — worth looking at as a
  template before building a new page type from scratch, especially for a term like Medicare whose
  deep dive (history, provisions, eligibility) overlaps with content `/history/` may already want to
  cover.

**Practical scoping implication:** "expand the glossary to three layers" is a mixed content +
coding issue. A content team can write `short`/`body`/deep-dive text for every term on the term
list once that list exists, but someone with front-end access needs to (a) turn layer 1 into an
actual hover/tap reveal instead of always-visible text, and (b) build wherever layer 3's deep-dive
pages live and how `conceptBox` links out to them. Splitting this into a content-issue and a
paired component-issue, rather than one issue assigned to one team, will avoid content getting
written with nowhere to land.
