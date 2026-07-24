# Handoff: ATTIA Consulting — Website & Brand System

## Overview
A minimalist, high-end one-page marketing site for **ATTIA Consulting** (independent strategy advisory, active since 1989; principal Karim H. Attia). Bilingual **DE/EN**, dark hero, restrained black/white/one-red palette, a Material-Design interaction layer, and a monochrome "ventures & affiliations" wall. This bundle also contains the full ATTIA design system the site is built on.

## About the Design Files
The files here are **design references created in HTML** — a working prototype showing the intended look and behaviour, **not production code to ship as-is**. The task is to **recreate this design in your target environment** using its established patterns and libraries (the prototype already uses idiomatic React). If no codebase exists yet, React + Vite is the natural choice; the components map 1:1.

- `reference/website.html` — the site as authored (consumes the design-system bundle via relative paths).
- `reference/website-standalone.html` — the **same site inlined into one self-contained file** (fonts, images, DS bundle all embedded). Open it directly in a browser to see the finished result; it is what was deployed to GitHub Pages. React/Babel load from the unpkg CDN (needs internet). For a build pipeline, precompile the JSX instead of shipping Babel-in-browser.

## Fidelity
**High-fidelity.** Final colours, typography, spacing, and interactions. Recreate pixel-for-pixel using the exact token values below.

## Tech in the prototype
React 18 (UMD) + in-browser Babel, plain inline styles keyed off CSS custom properties. The site composes six design-system components: `Logo`, `Eyebrow`, `Button`, `Tag`, `Card`, `Stat` (sources under `design_system/components/`). All styling flows from `design_system/styles.css` → `tokens/*.css`.

---

## Screens / Views (single page, in scroll order)

### 1. Sticky Header
- **Layout:** full-width, `position:sticky; top:0`, height **76px**, opaque white (`--ac-paper`), 1px bottom border (`--ac-line`). Inner container `max-width:1160px`, side padding **40px**, flex space-between. Gains a subtle shadow (`--md-e2`) once `scrollY > 8` (set via `data-elevated`).
- **Left:** `Logo` (network mark + "ATTIA / Consulting" wordmark), size 30.
- **Right (flex, gap 30px):** text links "Leistungen", "Über Karim"; a **DE/EN pill toggle** (`.lang`: 1px border, `border-radius:999px`; active button filled `--ac-ink`, white text); a small red `Button` "Kontakt".
- **Mobile (≤700px):** links/toggle/CTA collapse behind an animated hamburger (three 2px bars → X) into a full-width dropdown panel (opaque white, `--md-e2` shadow, items stacked with 1px dividers).

### 2. Hero  (`.hero`, background `--ac-graphite` #1C1C1E, white text)
- Container padding **104px top / 112px bottom**. Faint network mark bleeds off the top-right (`invert(1) grayscale(1)`, `mix-blend-mode:screen`, opacity .15).
- `Eyebrow` (light) "STRATEGIEBERATUNG · SEIT 1989"; then `h1` display type **74px**, weight 900, line-height 1, letter-spacing −.03em, max-width 920px — last word wrapped in `<em>` coloured `--ac-red`.
- Serif sub-line (`--font-serif`, 21px, `--text-ondark`).
- Two `Button`s: primary red "Gespräch vereinbaren" (lg) + outline "Leistungen" (lg, white border at 40% alpha). On mobile the CTA row stacks.

### 3. Services  (`#leistungen`, white)
- `.shead`: `Eyebrow` "Leistungen" + `h2` (display 42px/900) + serif intro.
- 3-column grid (`gap:24px`) of `Card accent interactive`. Each: red display number (01/02/03), 21px/700 title, serif body, an expand region (`.more`, animated `max-height`) revealed on click, and a red uppercase hint "Mehr ▾ / Weniger ▲".
- **Responsive:** 3 cols → 2 (≤900px) → **1 (≤700px)**.

### 4. Stats + capability band  (`.band`, `--ac-graphite`)
- **Top row** — three `Stat` cells (tone light: display value + tracked uppercase label with 3px red top rule), separated by 1px white-alpha verticals: `1989 / Aktiv seit`, `Global / Netzwerk`, `C-Level / Sparring`.
- **Below** — two labelled columns (`.lists2`, 1px top divider): **Technologiewellen** (Datenbanken · Internet · Internet der Dinge · Künstliche Intelligenz) and **Kernbranchen** (ERP · Marketing & Advertising · Health · Sustainability). Each item is 19px/600 white on a 1px row divider; the column heading is an uppercase red-ruled label. EN mirrors (Active since / Network / Sparring; Databases · Internet · Internet of Things · Artificial Intelligence; same industries).
- **Responsive:** top row 3→2 cols, list columns 2→1, cells switch to bottom borders (≤900px).
- Data lives in `T[lang]`: `stats3` (array of [value,label]), `bandWaves`+`waves`, `bandIndustries`+`industries`. All content is client-supplied — no invented figures.

### 5. About Karim  (`#ueber`, white)
- 2-col grid `340px / 1fr`, gap 56px. Left: portrait (`assets/karim-attia.jpg`, `border-radius:6px`, slight grayscale). Right: `Eyebrow` + a 26px serif statement (one word in italic red) + role block (`Karim H. Attia` / `Gründer & Geschäftsführer`) + a row of `Tag`s (first red, rest neutral): Datenbanken · Internet · IoT · Kryptografie · KI. → 1 col ≤900px.

### 6. Ventures & Affiliations wall  (`#netzwerk`, `--ac-graphite`)
- `.shead` (white variant) + a bordered grid (1px white-alpha, on top & left; each cell repeats right/bottom border). Cell: min-height 118px, padding 30×24, centered.
- Each cell: **wordmark** (`.nm`, 21px/700, color white@60%) + uppercase caption (`.nt`, 11px, white@40%). On hover the cell tints (white@4.5%), the wordmark goes solid white, and a **7px red dot** scales in before the name.
- **These are typeset wordmarks, not official logo files** (the real brand SVG/PNG assets could not be fetched at authoring time). Replace each `.nm` with the official logo `<img>` when assets are available; keep the caption. 17 entries in order: Xenion, Isobar, Dentsu Aegis Network, nugg.ad, Deutsche Post DHL, UBIRCH, IBM, BMG / RKI, GOVERNIFY, Coalition-X, Open Prometheus, IAB Europe, IAB US, BVDW, AGOF, agma, ZIA e.V. → 2 cols ≤900px.

### 7. Contact  (`#kontakt`, `--ac-paper-warm`, 1px top border)
- 2-col `1fr / 460px`, gap 64px. Left: `Eyebrow` + 40px display heading + info rows (Telefon `+49 172 4235533`, E-Mail `karim@attia.consulting`, Anschrift `Gorch-Fock-Haus · Breite Straße 159 · 22767 Hamburg`).
- Right: form (Name, E-Mail, Nachricht) — inputs 1.5px border, `--ac-red` focus border. Submit disabled (opacity .5) until name+email present; on submit the form swaps for a confirmation card (`.done`, 3px red top rule) addressing the user by first name. → 1 col ≤900px.

### 8. Footer  (`footer.site`, `--ac-ink`)
- Light wordmark `Logo` + legal line (address · USt-IdNr. DE247412700 · Geschäftsführer · © 2026).

### Floating action button (`.fab`)
- Fixed bottom-right, 60×60, `border-radius:18px`, red, `--md-e6` shadow, envelope icon. Scales/fades in after `scrollY > 520`; scrolls to contact.

---

## Interactions & Behavior
- **Language toggle:** `lang` state ('de' default) selects a `T[lang]` copy object; every string re-renders; `<html lang>` updates. Company names in the wall don't translate; their captions do.
- **Service cards:** single-open accordion (`open` index); `.more` animates `max-height` (`--dur-slow`) + opacity.
- **Material ripple:** delegated `pointerdown` spawns a `.rp` span (radial, scales to 2.6, .58s) on every `button` and service card.
- **Header elevation / FAB:** driven by `scroll` listeners at 8px / 520px thresholds.
- **Contact validation:** `name.trim() && email.trim()` gates submit; success state is local, no network.
- **Motion tokens:** standard easing `--md-ease` cubic-bezier(.4,0,.2,1); durations 140/240/420ms.

## State Management
`lang` ('de'|'en'), `open` (number|null, Services), form `{name,email,msg}` + `sent` (Contact), `show` (FAB), `open` (mobile menu, Header). All local `useState`; no data fetching.

## Design Tokens  (from `design_system/tokens/`)
**Color** — ink `#111111`, ink-soft `#3A3A3C`, ink-muted `#6E6E73`; paper `#FFFFFF`, paper-warm `#F7F5F2`, paper-sink `#EFEDE8`; **brand red `#BC0710`**, red-deep `#8C040B`, red-bright `#D81420`, red-tint `#F7E4E5`; line `#E3E0DA`, line-strong `#C9C5BD`, graphite `#1C1C1E`.
**Type** — display `Archivo Expanded` (900), sans `Archivo`, serif `Spectral` (Google Fonts; these are substitutions for the original Arial/system usage — swap if brand fonts are licensed). Scale 11→88px. Eyebrow label tracking .14em uppercase.
**Space** — 4/8/12/16/24/32/48/64/96/128. **Radius** — 0/2/4/8/pill. **Shadow** — sm/md/card/lg + Material `--md-e2/--md-e6`.

## Assets
- `assets/attia-logo.png` — the ATTIA "network of people" mark (extracted from the supplied PPTX, transparent PNG). Primary brand mark.
- `assets/karim-attia.jpg` — portrait of Karim H. Attia (supplied).
- Fonts via Google Fonts CDN. **No official third-party logos** for the wall — see §6.

## Files in this bundle
- `reference/website.html` — authored site (needs the DS bundle; see `design_system/`).
- `reference/website-standalone.html` — self-contained, runnable, deployed build.
- `design_system/` — `styles.css`, `tokens/*.css`, and the six component sources (`components/brand/`, `components/core/`) with their `.d.ts` + `.prompt.md`. The `.jsx`/`.d.ts` sources carry a trailing `.txt` (e.g. `Button.jsx.txt`) purely so this reference copy isn't recompiled by the source design system — drop the `.txt` when porting.
- `design_system/assets/` — the two images above.

## Notes for the developer
- Recreate with the codebase's own component library where equivalents exist; otherwise port the six components (they're ~40 lines each, inline-styled).
- Keep the palette discipline: **black + white + one red**. Red is an accent, never a surface wash. Corner radii stay small (0–8px). Shadows are quiet.
- The wall is the one place needing real assets — wire official logos before launch.
