# The Paragon Alliance — Policies & Statement of Intent

> [!IMPORTANT]
> **This is a school assignment.** The Paragon Alliance is a *fictional* New Zealand
> political party invented for a classroom exercise. It is not a registered party, it
> is not contesting any election, and nothing in this repository is a real policy or a
> real promise. The companies in the Paragon Tier register are invented and their
> scores are made up.
>
> Policies attributed to *real* parties are described as accurately as possible and
> every figure links to its original public source.

A single-page site setting out two policies for a fictional NZ party:

| # | Policy | Area |
|---|--------|------|
| 01 | **The Paragon Tier** — a government-recognised top tier of businesses that firms must compete to enter and can be removed from | Economy |
| 02 | **Sponsored Housing Districts** — companies fund and build whole districts, with affordability locked into a binding contract | Housing |

## Contents

```
index.html        the entire site — markup, styles and scripts in one file
assets/mark.svg   the TOPS emblem as a standalone vector
```

## Running it

There is no build step and no package manager. Open `index.html` in a browser.

To serve it locally instead:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

### Publishing to GitHub Pages

Settings → Pages → *Deploy from a branch* → select the branch and `/ (root)`.
GitHub serves `index.html` automatically.

## Implementation notes

- **No runtime dependencies.** The two interactive pieces are plain ES5-compatible
  JavaScript in an IIFE. An earlier draft loaded Vue 3 from a CDN; that was removed so
  the page works offline, on restricted school networks, and if a CDN is blocked.
- **Document layout.** The page is set as a long-form document rather than a landing
  page: a title block, a sticky contents rail, and numbered sections (1, 1.1, 1.2 …).
  Below 1000px the rail collapses to a two-column list above the body.
- **Flat by design.** No shadows, gradients, scroll animations or hover lifts. Warm
  ivory ground, near-black text, a single clay accent, and hairline rules carry the
  whole page.
- **Web fonts degrade gracefully.** Newsreader and Inter load from Google Fonts with
  `display=swap` and full local fallback stacks, so the page is readable before (or
  without) them.
- **Keyed DOM nodes.** The Tier register builds its rows once and reorders the same
  elements with `appendChild` on each re-score, so the score bars animate between
  cycles instead of being torn down and rebuilt.
- **Authored, not random.** The three scoring cycles are hard-coded so the register
  tells the same story every time: a bank losing its place, a small software firm
  earning one, and a firm that fell out climbing back in.
- **Accessibility.** Skip link, visible focus rings, `aria-pressed` on the segmented
  control, a `role="status"` live region on the district verdict, and a
  `prefers-reduced-motion` path that disables all transitions.
- **Print stylesheet.** The contents rail and interactive panels are dropped, each
  section starts a new page, and link targets are expanded after their text.
- **`noindex`.** The page asks search engines not to index it — it is a fictional
  political platform and should not surface in search results as though it were real.

## Sources

All ten sources are listed at the bottom of the page with links, and were checked on
14 September 2026.
