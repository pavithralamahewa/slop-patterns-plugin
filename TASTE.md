# Taste

Read this before you generate UI. It is a short rule set for Cursor and Claude Code, taken from nine hand-checked entries in [Slop Patterns](https://sloppatterns.com) by Precious Studio. One of these on a page can be a choice. Several together make the product look like every other generated page.

Follow every do and don't when you write or change HTML, CSS, JSX, Tailwind, Vue, or Svelte. If the user asked for that style, keep it and say so. When you drop a pattern, replace it with a form that fits the product.

Each code links to the full entry on [sloppatterns.com](https://sloppatterns.com).

## [A3](https://sloppatterns.com/#three-identical-feature-cards). Three identical feature cards

Tell: a row of exactly three equal cards. Each card has an icon, a short title, and about two lines of text. The same row comes back for benefits, then steps, then testimonials.

Why it reads as AI-made: the three-column feature grid is the features block in Tailwind and in template libraries. Models have seen it next to the word "features" so often that they treat equal cards as the only way to list things. They give every item the same weight because they cannot rank them.

- Do: rank the features. Give the lead one more room, a real screenshot, and a longer explanation. Use a different form when the content is different: a comparison table, a list, or one annotated image.
- Don't: lay features out as three, four, or six identical cards with the same icon tile, heading length, and body length.

## [A10](https://sloppatterns.com/#gradient-text-headline). Gradient text headline

Tell: the main heading, or a big number, is filled with a gradient, often indigo to pink or white to grey, sometimes only on the second line. That gradient rarely matches any other colour on the page.

Why it reads as AI-made: clipping a gradient to text is a Tailwind trick from hero demos and starter templates. Models apply it whenever they write a hero, as a default flourish.

- Do: set the headline in one solid colour with strong contrast, and let the words carry it. If one word needs emphasis, colour that word in the accent, solid.
- Don't: paint an h1, a large heading, or a stat with a gradient.

## [A15](https://sloppatterns.com/#emoji-as-icons). Emoji as icons

Tell: feature cards, nav items, and lists lead with a rocket, lightning bolt, padlock, or similar emoji at icon size. The glyphs differ on every operating system and sit off the text baseline.

Why it reads as AI-made: emoji cost a text model nothing. No import, no file, no icon set. Chat habits also drop emoji into the answer, and that habit lands in the interface when nobody named an icon set.

- Do: use one icon set with one stroke weight, sized to the type, or use no icons. For personality, use a small custom set.
- Don't: use emoji as the icon system.

## [A22](https://sloppatterns.com/#crushed-headline-tracking). Crushed headline tracking

Tell: display headlines, often 60px and up, are tracked so tight the letters touch. Weight is heavy and line height is near 1. Body text sometimes goes the other way and is tracked wide.

Why it reads as AI-made: Tailwind's tight-tracking classes, and marketing pages from 2022 to 2024, taught models that "modern" means crushed display type. They copy the class and never check whether that typeface is already tight.

- Do: set tracking for the typeface and the size. Most display faces need no tighter than -0.02em. Body text stays at 0. Check the headline on a phone, where the same tight tracking meets a smaller size.
- Don't: put tracking-tight or tracking-tighter on every headline, or wide tracking on body text.

## [A23](https://sloppatterns.com/#shouting-section-labels). Shouting section labels

Tell: every section opens with a tiny uppercase label, widely tracked, in the accent colour: FEATURES, HOW IT WORKS, TESTIMONIALS. A dot or a thin line sometimes sits beside it. The heading underneath says the same thing.

Why it reads as AI-made: the eyebrow label is a stock piece of Tailwind UI and marketing blocks. Models stamp it on every section because it was part of the section template, even when it adds nothing.

- Do: delete a label that repeats the heading. If a category label earns its place, write it in sentence case and make it say something the heading does not.
- Don't: open sections with small uppercase text that restates the heading.

## [A36](https://sloppatterns.com/#the-pulsing-dot). The pulsing dot

Tell: a small green or accent dot pulses forever beside words that never change: Live, Now in beta, All systems operational, AI online. It shows up in the hero, the nav, and the footer.

Why it reads as AI-made: Tailwind's ping animation and status dots on product sites taught models to hang a pulse on any status-like phrase. It is two classes and no dependency, so it survives every edit.

- Do: show a status dot only when it is tied to real state. Keep it still unless something just changed.
- Don't: add a pulsing or pinging dot as decoration.

## [A47](https://sloppatterns.com/#blank-tab-blank-preview). Blank tab, blank preview

Tell: the browser tab still shows the Vite, Next.js, or Create React App icon, or a generic globe. The title reads Vite + React, Create Next App, or My App. Pasting the link into a chat app gives no preview, or a blank one. The page itself can look finished.

Why it reads as AI-made: generators start from a framework starter and spend their effort on the visible page, so the document head is never edited. A default favicon and a missing share image are among the fastest signs of a generated site.

- Do: ship a real favicon set, a 1200 by 630 share image that shows the product, and a title and description written for this page. Open the link in a chat app and look at the preview before you call it done.
- Don't: leave the framework favicon, a placeholder title, or a page with no share image.

## [A55](https://sloppatterns.com/#skipped-heading-level). Skipped heading level

Tell: an h1 is followed by an h3, or later by an h5, because that tag was the size that looked right. On screen the type looks fine. In the page outline there are holes.

Why it reads as AI-made: models pick heading levels by visual weight, and they build one component at a time without knowing which level the rest of the page is on.

- Do: nest headings in order. h2 under h1, h3 under h2. Change the size in CSS.
- Don't: choose h1 to h6 to get a font size.

## [B115](https://sloppatterns.com/#landmark-free-page). Landmark-free page

Tell: the page is nested divs. There is no header, no nav, no main, and no footer, so assistive technology has nothing to jump between. Prices, plan names, and headings are divs with font-size classes.

Why it reads as AI-made: utility-class templates use a div for every box. Header, nav, main, and footer change nothing on screen, so the model leaves them out.

- Do: wrap the page in header, nav, main, and footer. Use a single h1 and a heading outline that does not skip a level.
- Don't: build the page from divs alone.

## Wire this in

**Cursor.** Copy this file to `.cursor/rules/taste.mdc`. Cursor reads rules in that folder. Put this front matter at the very top so the rule loads when UI files are open:

```
---
description: Follow before writing UI. Blocks common generated-interface defaults.
globs: ["**/*.html", "**/*.css", "**/*.scss", "**/*.jsx", "**/*.tsx", "**/*.vue", "**/*.svelte"]
alwaysApply: false
---
```

**Claude Code.** Leave this file at the project root. Add this line to `CLAUDE.md`:

```
Before you write or change UI, follow @TASTE.md.
```

Source: [Slop Patterns](https://sloppatterns.com) by Precious Studio. Tells and fixes are condensed from the pattern library.
