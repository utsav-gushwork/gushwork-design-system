# Gushwork Design System

A working design system for **Gushwork** — the AI Marketing Team that researches, writes, publishes, and ranks content across AI search engines (ChatGPT, Perplexity, Gemini) and traditional search, then turns the resulting traffic into qualified leads delivered straight to your inbox.

This system is the source of truth for Gushwork's marketing surfaces. Use it whenever you design or build anything that needs to look like Gushwork — landing pages, decks, case studies, ads, product screens.

---

## 1. What you're looking at

```
Gushwork Design System/
├── README.md                 ← you are here
├── SKILL.md                  ← skill manifest for Claude Code / agents
├── colors_and_type.css       ← all tokens (colors, type, spacing, radii, shadow)
├── fonts/                    ← Vert Grotesk Display (display typeface)
├── assets/                   ← logos, avatars, case-study images, curve patterns
├── preview/                  ← the design-system "cards" surfaced in the review tab
└── ui_kits/
    └── website/              ← marketing-site UI kit (hi-fi recreation)
        ├── index.html
        └── components/       ← Header, Hero, ClientLogos, CaseStudyCard, etc.
```

### Source materials this was built from
- **Figma** — `GW-Design-Elements.fig`, mounted as a virtual filesystem. Core token frames at `/Core-Components/{Color,Typography,Spacing,Radius,Effect}-System`. Marketing components at `/Webpages/`, `/Folds/`, `/Base-Components/`. Client logos at `/Client-Logos/`.
- **Website** — https://www.gushwork.ai/ (visual + voice reference).
- **Uploads** — Vert Grotesk Display VF.ttf + four Gushwork logo SVGs (white & dark, full + icon-only).

---

## 2. Brand context

**Who Gushwork serves.** Founders and growth leads at B2B SaaS and consumer companies who need pipeline from organic search, AI search, and content — but don't want to run a content team.

**What Gushwork sells.** A managed service that behaves like a senior marketing team: researches keywords across Google + LLMs, writes and publishes long-form content, builds backlinks, and pipes qualified leads into your inbox. The "AI" angle is the differentiator — Gushwork ranks you in *AI* answer engines, not just Google's blue links.

**The promise.** Inbound leads. Measurable traffic growth. Real customer outcomes (1.3M search impressions, 55%+ visitor growth, 56× market presence). Numbers, not adjectives.

**Standard primary CTA copy** is **`Book a demo`** (sentence case, no period) and it always links to `/demo`. Don't reword it per page ("Talk to an expert," "Get started," etc.) — consistency is the point on conversion surfaces.

---

## 3. Content fundamentals

Voice should sound like **a confident senior strategist talking to a busy founder.** Direct, plainspoken, results-led. Never feature-jargon. Never hype.

### Tone & casing
- **Sentence case** for headings, buttons, eyebrows. (`Talk to an expert`, not `Talk To An Expert`.) Exception: UPPERCASE micro-labels for section eyebrows in token sheets (`PRIMARY`, `SHADOWS`).
- **Title case** is OK for product/service nouns in body (`AI Search Engines`, `Content & SEO`).
- **First person plural for the company, second person for the reader.** "We do X. You get Y." Avoid "I."
- **No exclamation marks.** No emoji on marketing surfaces. (Internal/blog tone may relax this.)
- **No italics in display / heading copy.** Italics in Vert Grotesk Display read as a different voice and break the calm, declarative tone. Use weight (600 → 700), color, or a chip eyebrow for emphasis instead. Italics are OK inline in long-form body copy only (citations, foreign words, book titles).
- **Never signal status with a bare colored dot.** No green dot for "Live," no blue dot for "New," no traffic-light pucks. Use a Phosphor icon at 13–16px in the matching weight — `ph-fill ph-broadcast` for live, `ph-fill ph-sparkle` for new, `ph-fill ph-check-circle` for shipped. Color comes from the icon's `currentColor`, not from a separate puck. The new `GWSectionEyebrow` component bakes this rule in.
- **Oxford commas** on. Curly quotes (`"…"`, `'…'`) on. Em-dashes for asides.

### Vocabulary
- Inbound leads. Qualified leads. Pipeline. Search impressions. AI search. Traffic.
- "AI Marketing Team," "AI search engines," "rank you," "publish for you."
- Avoid: "synergy," "best-in-class," "next-gen," "revolutionize," "unlock."

### Patterns from the Figma source
- Hero pattern: a confident claim + a hard number. Example testimonial pulled from Figma: *"Within a year, our website visitors have grown by over 55%, and our search impressions have surpassed 1.3 million."* Cited to a real founder, real company.
- Section CTA pattern: a one-line claim with a single black button. *"See how we can do the same for you."* → `Talk to an Expert`.
- Case study titles open with a verb of impact: *"How Hyper Specific Search Targeting Skyrocketed Pocketly's Market Presence by 56x."*

---

## 4. Visual foundations

### Color
The palette is **deliberately calm and corporate**: 90% black-on-white, 10% a clear, saturated blue. There are no gradients, no glows, no purples. The blue does heavy lifting — primary CTAs, hero backgrounds, link text. Slate (`#111827`) is reserved for heading on light. Reds/greens/yellows only for semantic states.

- **Primary:** `#0070FF` (Blue 500). Hover/pressed: `#0061E0` (Blue 600). Tints: `#CCE2FF` (Blue 100), `#E5F1FF` (Blue 50) for soft surfaces, light testimonial text.
- **Neutrals:** Pure black `#0D0D0D` for primary text. Slate `#262A2E` and `#535A61` for secondary. `#E1E3E8` is the default border. `#F7F8F9` is the canonical "subtle background" wash.
- **Semantic:** Success `#1FC16B`, Warning `#FFDB43`, Error `#FB3748`.
- **Inverse surfaces** (deep blue hero, dark testimonial): `#0070FF` background with white type and `rgba(255,255,255,0.10)` borders.

### Typography
Two faces, no more.

- **Vert Grotesk Display** — geometric grotesk for all headings, hero copy, large quotes, callouts. Bold (700) and Semibold (600) carry display work; Medium (500) for h6/h7. Crisp tracking: `-0.016em` on large display sizes.
- **Inter** — every byte of body, UI, navigation, button labels, captions. Regular/Medium/Semibold. Line-height ~1.6 for body, ~1.4 for tight quotes, 1.2 for headings. Tracking `-0.006em` is the workhorse.

The contrast between Vert Grotesk's display-weight forms and Inter's neutral UI rhythm *is* the typographic identity. Never substitute. (If you must, fall back to Inter for both — never let display headings render in a generic system serif.)

### Spacing
A geometric scale built around multiples of 4: `4, 8, 12, 16, 20, 24, 32, 40, 48, 56, 60, 80, 100, 120, 160`. Section padding on marketing pages tends to be `100px` top, `56px` bottom, with `80px` between sections. Card internal padding is `20–32px`.

### Radii & shape language
- **Buttons** — `10px` (regular 44h) and `12px` (large 52h). Never fully rounded except for chips.
- **Chips / eyebrows** — `999px` pill.
- **Cards** — `24px` (`--gw-radius-8`). Card *images* inset are `16px`. The signature hover tell is asymmetric radius `24 24 60 24` (`--gw-radius-card-hover`) — codified on pillar/agent cards. Reach for it whenever a card on a white surface needs to read as interactive; never use it on dark hero cards or on tiles inside a list view.
- **Sections / canvas** — `40px` corner rounding on white "page" surfaces and inverse blue heroes.
- **Fold stacking** — every top-level `<section>` after the first carries `border-top-left-radius: 20px; border-top-right-radius: 20px; margin-top: -20px;`. Use the `--gw-fold-radius` token (20px). This is the marketing layout's signature rhythm — folds visibly stack onto one another rather than abutting. Don't apply to the first fold (the hero); don't apply to the footer.

### Borders
- Default UI border: `1px solid #E1E3E8`.
- On photographic / dark surfaces: `1px solid rgba(255,255,255,0.10)`.
- Cards on white use either the neutral border OR the soft ink overlay `rgba(1,1,9,0.10)` — never both.

### Shadows / elevation
A short ramp, all subtle. Gushwork does not punch shadows.
- **S1** `0 1px 2px rgba(10,13,20,0.03)` — flat surface hint
- **S2** `0 3px 50px rgba(0,0,0,0.07)` — the canonical card resting shadow (very soft, very wide)
- **S3** `0 16px 32px -12px rgba(88,92,95,0.10)` — card hover lift
- **S4** `0 24px 64px -16px rgba(0,0,0,0.18)` — modals only
- **Focus ring** `0 0 0 4px #F1F1F3, 0 0 0 2px #FFFFFF` (high-contrast button focus)

### Backgrounds & textures
- Default page: pure white `#FFFFFF`, with sections optionally on `#F7F8F9` wash.
- **Hero / testimonial blocks**: solid `#0070FF` with **two overlaid concentric curve outlines** (the only "graphic" motif in the system — see `assets/curve-pattern.svg`). White stroke, 4px width, ~10% opacity. Read as a horizon line, not as decoration.
- **Curve pattern scope — large blue panels only.** Use the curve on full-bleed hero / CTA / testimonial folds where the entire panel is `var(--gw-bg-brand)`. Do **not** layer the curve onto inner result panels inside white cards (e.g. a stat strip inside a case-study card): it adds noise and competes with the card's content rhythm. If a smaller blue surface needs visual interest, lean on the chip eyebrow or numeric stats instead.
- No gradients. No mesh. No noise. No grain.
- Photography is full-color, mostly product/team shots, kept warm but unfiltered. Avatars are circle-cropped 48px or 56px.

### Motion
Restrained. The brand favors stillness with crisp transitions, not bouncy animation.
- Hover transitions: 120–200ms, easing `cubic-bezier(0.22, 1, 0.36, 1)`.
- Buttons: background color crossfade, no scale change.
- Cards: shadow + 1px translate-y on hover.
- Page-level: gentle fades on scroll, no parallax, no auto-play video.

### Interactive states
- **Hover (filled buttons):** shift to darker tier (`#0070FF → #0061E0`); no shadow added.
- **Hover (ghost / stroke):** add `rgba(1,1,9,0.04)` background tint.
- **Pressed:** drop another tier (`#0061E0 → #0048A3`) or background `rgba(1,1,9,0.08)` on light.
- **Focus:** the focus ring shadow described above. Never an `outline: blue`.
- **Disabled:** `background #E1E3E8`, text `#959BA4`.

### Layout rules
- Marketing pages are a max **1240px** content column with **100px** outer page padding. Nav and footer span full bleed; everything inside aligns to the column.
- **Folds stack.** Every `<section>` after the first uses `border-top-left-radius` / `border-top-right-radius: var(--gw-fold-radius)` (20px) and `margin-top: -20px`. The hero is flat-topped; everything below pulls up over its predecessor.
- Two-column splits (testimonial quote + author card): **793 / 320** with auto gap.
- Cards in grids: **400px** wide standard, **3-up** below 1240, **2-up** below ~900.
- Section CTAs are **full-width** "claim + button" bars inside `#F7F8F9` rounded blocks at the bottom of dark heroes.
- **Trust marquee.** 24s linear infinite loop, `gap: 56px`, logos rendered at **30px height**, `opacity: 0.72`, `filter: grayscale(1) contrast(0.95)`. Edge fade: `mask-image: linear-gradient(to right, transparent, #000 8%, #000 92%, transparent)`. No pause-on-hover. No tilt. Same spec everywhere the marquee appears.
- **Marketing header (conversion variant).** On landing pages, drop the nav links entirely. Logo on the left → homepage; single primary CTA on the right (`Book a demo` → `/demo`). The full nav header is for the marketing site shell; the conversion header is for any page whose only job is to drive demo bookings. See `GWMarketingHeader`.

### Use of transparency / blur
- Glass / blur is **not** part of this system. If you find yourself reaching for `backdrop-filter`, stop.
- Transparency only appears as white-on-blue (`rgba(255,255,255,0.10)` borders) or as the ink overlay for soft borders on white.

---

## 5. Iconography

**Phosphor Icons** is the chosen icon set. The Figma file ships 1,270 Phosphor frames — every common UI icon, multiple weights (Regular, Bold, Fill).

- **Default weight:** `Regular` for navigation and inline text. `Bold` inside buttons (so the icon reads at the same optical weight as Inter Medium 14). `Fill` for filled-chip glyphs.
- **Size grid:** 14, 16, 20, 24px. 16px is the workhorse for inline + button-trailing icons.
- **Color:** inherits text color via `currentColor`. Never tint icons a custom hue — they pick up `--gw-fg-1/2/3` or the surface inverse.
- **Library load:** linked from CDN — `https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2`. We do not ship a local sprite.
- **No emoji.** None. Not as bullets, not as decoration, not in feature lists.
- **Brand marks** for client logos live in `assets/logos/` (PNG). The Gushwork logo lives in `assets/gushwork-logo.svg` (dark text version) and `assets/gushwork-logo-white.svg` (inverse).
- **Decorative graphic motif:** the curved-horizon SVG pattern (`assets/curve-pattern.svg`) is the *only* recurring illustration. It only appears on solid-blue hero / testimonial blocks at low opacity.

---

## 6. Caveats & substitutions

- **Inter** — no .ttf was supplied, so it's loaded from Google Fonts. Pixel-identical to the Figma source; safe substitution.
- **Vert Grotesk Display** is a *variable* font (single .ttf, weights 100–900). Behaves correctly across all the weight tiers the system declares.
- **Phosphor icons** — original Phosphor library via CDN, same icon set as the Figma frames. No substitution.
- The Figma's "Tertiary" color group (slate `#111827` and friends) is included as `--gw-tertiary-*` but used very sparingly in practice — mainly as the H4-H6 color on white backgrounds where the pure black feels too heavy. Most surfaces use `--gw-fg-1` (black).

---

## 7. Index — where to look for what

| If you need… | Open… |
|---|---|
| Raw design tokens (CSS vars) | `colors_and_type.css` |
| Logo files (light/dark, full/icon) | `assets/gushwork-logo*.svg`, `assets/gushwork-icon*.svg` |
| Case-study imagery & avatars | `assets/case-study-*.png`, `assets/avatars/*.png` |
| Curve graphic for hero backgrounds | `assets/curve-pattern.svg`, `assets/curve-pattern-2.svg` |
| Token cards (registered in review pane) | `preview/*.html` |
| Live website UI kit | `ui_kits/website/index.html` |
| Agent / Claude Code skill manifest | `SKILL.md` |

## 8. UI kit components (marketing surfaces)

Live in `ui_kits/website/components/`. Use these — don't reinvent.

| Component | When to use |
|---|---|
| `GWButton` | Every clickable action. Variants: `blue` (primary), `black`, `white`, `stroke-black`, `stroke-white`, `ghost-blue`, `lighter`. |
| `GWChip` | Inline tag chips (USA, Fintech, 100+ employees). Pill, 28h. |
| `GWSectionEyebrow` ★ | **The canonical eyebrow.** White pill above section headings, Phosphor icon (fill weight, blue, 13px) on the left. Pass `tone="dark"` on dark folds. Replaces the old blue-tinted eyebrow pill — and is the only acceptable way to badge a section. |
| `GWSquareIconButton` ★ | 56×56 white square, 16px radius, S1 → S2 hover. Used as paired prev/next on the case-study carousel and as standalone "open detail" controls. |
| `GWSection` | Generic 1240-column section wrapper with 96px vertical padding. Use `padded={false}` for flush blue heroes. |
| `GWHeader` | Full marketing nav header (logo · Platform ▾ · Customers · Blog · Pricing · `Book a demo`). For the marketing site shell. |
| `GWMarketingHeader` ★ | **Conversion variant.** Logo + single primary CTA, no nav links. Use on `/demo`, vertical landers, ad-driven entries. |
| `GWHero` | Site hero with rotating engine name, inline email capture, product video frame, trust marquee. |
| `GWInboundEngine`, `GWStatsCompound`, `GWAgentGrid` | Mid-page narrative folds. |
| `GWCustomerVideos` | 3-up dark video testimonial wall. For the "Don't just take our word for it" fold. |
| `GWCaseStudyCarousel` ★ | **One-up case-study spotlight.** 480px portrait video frame on the left (radial-gradient + frosted initials + play + name overlay), 32px display quote + "Read more →" + hairline-separated 3-up stats on the right. Paired square arrow nav top-right. No pip indicators. |
| `GWCTAFold` | The blue CTA panel above the footer. Carries the curve pattern. |
| `GWFooter` | Dark footer. Platform / Company columns + tel + mailto + real social URLs. Filled-gradient wordmark (no longer the stroked treatment, which clipped at common widths). Pass `wordmark={false}` to hide it entirely. |

★ = added in the latest manufacturing-vertical pass. If you're updating an older surface, replace the old equivalents with these.
