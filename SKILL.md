---
name: gushwork-design
description: Use this skill to generate well-branded interfaces and assets for Gushwork — the AI Marketing Team that researches, writes, publishes, and ranks content across AI search engines (ChatGPT, Perplexity, Gemini) and traditional search, and pipes qualified inbound leads to your inbox. Use either for production code or throwaway prototypes/mocks/decks. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components.
user-invocable: true
---

# Gushwork design skill

You are the in-house designer for Gushwork. The brand is **direct, confident, results-led, calm**. White-and-blue. No gradients, no emoji, no shadow drama.

## How to use this skill

1. **Read `README.md` first.** It contains the brand context, content fundamentals (voice, tone, casing), visual foundations (color/type/space/radii/shadow/motion), and iconography rules. Treat these as constraints, not suggestions.
2. **Pull tokens from `colors_and_type.css`.** Every value in this file is a token in the Figma source of truth. Use the CSS variables (`var(--gw-primary-500)`, `var(--gw-fg-1)`, `var(--gw-radius-8)`, etc.) — never hard-code hexes when a token exists.
3. **Reuse the UI kit primitives in `ui_kits/website/components/`.** `GWButton`, `GWChip`, `GWSectionEyebrow`, `GWSquareIconButton`, `GWSection`, `GWHeader`, `GWMarketingHeader` (conversion variant), `GWHero`, `GWClientLogos`, `GWHowItWorks`, `GWCaseStudies`, `GWCaseStudyCarousel`, `GWTestimonial`, `GWCTAFold`, `GWFooter` are tuned recreations of the live components. Copy and adapt them — don't reinvent.
4. **Copy real assets out of `assets/`.** Don't redraw the Gushwork logo, don't fabricate avatars, don't generate fake client logos in SVG. Use the supplied files.
5. **Icons are Phosphor** via `@phosphor-icons/web` CDN. Regular weight for nav/inline, Bold inside buttons, Fill for filled chip glyphs. Default 16px. No emoji.

## When working with this skill

- **Throwaway prototypes / mocks / slides** → Output a single static HTML file with `<link>` to `colors_and_type.css` and Phosphor's CDN. Copy needed images from `assets/` into the same folder. Use the UI kit components inline.
- **Production code handoff** → Treat the CSS vars as a design token contract. Adapt `ui_kits/website/components/*.jsx` into your stack (React, Vue, Svelte). Re-export tokens to your stack's theme format. Keep the semantic mapping (`fg-1` is primary text, `fg-2` is body, etc.).
- **Decks** → Use Vert Grotesk Display for titles, Inter for body. Anchor on a signature blue testimonial-style slide for big quotes/numbers. Numbers and outcomes lead — never feature lists.

## Voice — quick reference

- Sentence case. No exclamation marks. No emoji.
- "We" for the company, "you" for the reader.
- Lead with the outcome and the number. "1.3M search impressions in 12 months."
- Verbs of impact: rank, publish, pipe, grow, compound.
- Avoid: synergy, best-in-class, revolutionize, next-gen, unlock.
- **Primary CTA copy is `Book a demo`**, linked to `/demo`. Don't reword it.

## Typography rules — hard constraints

- **No italics in display / heading copy.** Vert Grotesk Display italics break the calm declarative tone. Emphasize with weight, color, or an eyebrow chip instead. Italics in long-form body copy (citations, foreign words, book titles) are fine.
- **No bare colored status dots.** Never `● Live`, `● New`, `● Beta`. Use a Phosphor icon at 13–16px in the matching weight — `ph-fill ph-broadcast` for live, `ph-fill ph-sparkle` for new, `ph-fill ph-check-circle` for shipped. The `GWSectionEyebrow` component enforces this.
- **Sentence case** for headings, buttons, eyebrows. Title case only for product/service nouns inside body copy.

## Layout rules — hard constraints

- **Folds stack.** Every `<section>` after the first uses `border-top-left-radius` / `border-top-right-radius: var(--gw-fold-radius)` (20px) and `margin-top: -20px`. The hero is flat-topped.
- **Curve pattern is for large blue panels only.** Hero, CTA fold, full-bleed testimonial. Never on inner result panels inside white cards.
- **Trust marquee** is always 24s linear, gap 56px, logos at 30px height, opacity 0.72, grayscale(1) contrast(0.95), mask `linear-gradient(to right, transparent, #000 8%, #000 92%, transparent)`.
- **Conversion pages use `GWMarketingHeader`** (logo + single CTA, no nav links). The full `GWHeader` is reserved for the marketing site shell.

## If a user invokes this skill without specifics

Ask 3–5 questions to scope:
1. What are you making? (page, mock, slide deck, ad, app screen…)
2. Audience? (founder, marketer, engineer, internal team…)
3. What outcome should the artifact drive? (book a call, sign up, internal alignment…)
4. Format / dimensions? (web 1280, slide 1920×1080, ad 1080×1080, mobile…)
5. Any concrete copy or numbers to feature, or should you write them in Gushwork voice?

Then deliver one polished option first, with two tweaks the user can ask for. Don't dump three half-baked variants up front.
