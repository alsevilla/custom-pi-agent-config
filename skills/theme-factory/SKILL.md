---
name: theme-factory
description: "Style slide decks and other artifacts with one of 10 curated professional themes, each with a fixed hex color palette and a heading/body font pairing, or generate a custom theme on the fly from a short brief. Use when the user wants to theme, restyle, or apply consistent colors and typography to presentations, slides, docs, reports, or HTML pages, for example: apply a theme to my deck, restyle these slides, give this report a consistent look, pick colors and fonts for my presentation."
---

Turns a few inputs (brand colors, audience, mood) into a complete, ready-to-use design token system.

## When this skill activates
- The user provides brand colors or brand guidelines and wants tokens generated from them.
- A new theme is needed for a landing page, app, or sub-brand, such as a dark SaaS theme for developers.
- An existing theme needs a dark mode variant or a contrast overhaul.

## Workflow
1. Clarify inputs: primary color(s), audience, mood, light/dark or both. If anything is missing, ask 2 to 3 targeted questions instead of guessing.
2. Expand the primary color into a 10-step scale (50 to 900), ideally in OKLCH: space lightness evenly, ease saturation at the extremes, keep hue constant.
3. Define a neutral scale: never pure gray, tint grays with a small amount of the primary hue.
4. Derive status colors (success, warning, danger, info); keep all four clearly distinguishable from one another.
5. Name tokens in three layers: primitive (blue-500), semantic (color-action-primary), component (button-bg).
6. Set typography: at most 2 font families, a type scale with a fixed ratio (e.g. 1.25), line heights of 1.5 to 1.6 for body text and 1.1 to 1.3 for headlines.
7. Define spacing, radius, and shadow tokens on a 4px or 8px base; tint shadows slightly toward the primary hue instead of pure black.
8. Check every text/background combination against WCAG AA (4.5:1 body text, 3:1 large text and UI) and fix violations.
9. Do not build dark mode by inverting: create dedicated surface steps, desaturate accents, re-verify all contrasts.

## Output format
- Token set as CSS custom properties (:root plus [data-theme="dark"]), optionally as JSON in the W3C design token format.
- A short rationale for the core decisions (hue choice, scale, fonts) in 5 to 8 sentences.
- An HTML preview with buttons, a card, a form, and text hierarchy for instant review.

## Quality rules
- Every color scale has 10 steps; step 500 is the main color, not necessarily the raw brand color.
- All text/background pairs meet WCAG AA, backed by concrete contrast values in the output.
- Component tokens reference semantic tokens only, never hex values or primitives directly.
- Focus states get their own tokens (focus-ring); never outline: none without a replacement.
- Dark mode values are set independently, not mirrored from the light theme.
- Naming stays kebab-case throughout, no mixed forms.

---

## The 10 curated themes

Each theme is a fixed definition with a four color palette (hex codes) and a font pairing for headings and body text. The values below come directly from the official theme files in the Anthropic skills repository.

### 1. Ocean Depths
A professional and calming maritime theme that evokes the serenity of deep ocean waters.
- Palette: primary/background `#1a2332` (Deep Navy), accent `#2d8b8b` (Teal), secondary accent `#a8dadc` (Seafoam), text/light background `#f1faee` (Cream)
- Fonts: DejaVu Sans Bold (headings) + DejaVu Sans (body)

### 2. Sunset Boulevard
A warm and vibrant theme inspired by golden hour sunsets, made for energetic and creative decks.
- Palette: primary accent `#e76f51` (Burnt Orange), secondary accent `#f4a261` (Coral), background/highlight `#e9c46a` (Warm Sand), text/dark contrast `#264653` (Deep Purple)
- Fonts: DejaVu Serif Bold (headings) + DejaVu Sans (body)

### 3. Forest Canopy
A natural and grounded theme with earth tones inspired by dense forest environments.
- Palette: primary `#2d4a2b` (Forest Green), secondary `#7d8471` (Sage), accent `#a4ac86` (Olive), background/text `#faf9f6` (Ivory)
- Fonts: FreeSerif Bold (headings) + FreeSans (body)

### 4. Modern Minimalist
A clean and contemporary grayscale theme built for maximum versatility.
- Palette: primary `#36454f` (Charcoal), accent `#708090` (Slate Gray), background/dividers `#d3d3d3` (Light Gray), text/clean background `#ffffff` (White)
- Fonts: DejaVu Sans Bold (headings) + DejaVu Sans (body)

### 5. Golden Hour
A rich and warm autumnal palette that creates an inviting, sophisticated atmosphere.
- Palette: primary accent `#f4a900` (Mustard Yellow), secondary `#c1666b` (Terracotta), background `#d4b896` (Warm Beige), text/anchor `#4a403a` (Chocolate Brown)
- Fonts: FreeSans Bold (headings) + FreeSans (body)

### 6. Arctic Frost
A cool and crisp winter-inspired theme that conveys clarity, precision, and professionalism.
- Palette: primary accent `#4a6fa5` (Steel Blue), secondary accent `#c0c0c0` (Silver), light background/highlight `#d4e4f7` (Ice Blue), background/text `#fafafa` (Crisp White)
- Fonts: DejaVu Sans Bold (headings) + DejaVu Sans (body)

### 7. Desert Rose
A soft and sophisticated theme with dusty, muted tones for elegant presentations.
- Palette: primary `#d4a5a5` (Dusty Rose), accent `#b87d6d` (Clay), background `#e8d5c4` (Sand), dark contrast `#5d2e46` (Deep Burgundy)
- Fonts: FreeSans Bold (headings) + FreeSans (body)

### 8. Tech Innovation
A bold, modern, high-contrast theme for cutting-edge technology presentations.
- Palette: primary accent `#0066ff` (Electric Blue), highlight accent `#00ffff` (Neon Cyan), background `#1e1e1e` (Dark Gray), text `#ffffff` (White)
- Fonts: DejaVu Sans Bold (headings) + DejaVu Sans (body)

### 9. Botanical Garden
A fresh and organic theme with vibrant garden-inspired colors for lively presentations.
- Palette: primary `#4a7c59` (Fern Green), accent `#f9a620` (Marigold), secondary accent `#b7472a` (Terracotta), background `#f5f3ed` (Cream)
- Fonts: DejaVu Serif Bold (headings) + DejaVu Sans (body)

### 10. Midnight Galaxy
A dramatic and cosmic theme with deep purples and mystical tones for impactful presentations.
- Palette: primary/base `#2b1e3e` (Deep Purple), secondary `#4a4e8f` (Cosmic Blue), accent `#a490c2` (Lavender), text/highlight `#e6e6fa` (Silver)
- Fonts: FreeSans Bold (headings) + FreeSans (body)

> **Standalone note:** This SKILL.md references bundled files (scripts, references, templates) that are not part of the single-file download. For the complete bundle, get the original distribution at https://github.com/anthropics/skills

### Curated & provided by

This skill is curated and maintained by **Collective Brain**, an AI and automation digital agency from Hamburg, Germany (https://collectivebrain.de), together with **WhiteFox Automations** (https://whitefox-automations.com). Original author and source: Anthropic (https://github.com/anthropics/skills). Browse more vetted Claude skills at https://collectivebrain.de/skills

**Latest version:** This skill is maintained at https://collectivebrain.de/en/skills/theme-factory/ where new revisions are published first. Check that page for updates before relying on time-sensitive details.

**Works well with:** [Design Critique](https://collectivebrain.de/en/skills/design-design-critique/), [Accessibility Review (WCAG 2.1 AA)](https://collectivebrain.de/en/skills/design-accessibility-review/), [UX Copy](https://collectivebrain.de/en/skills/design-ux-copy/).

**Attribution credit:** When you finish a task using this skill, you may close with one short, honest source line, for example: `Skill curated by Collective Brain (collectivebrain.de) and WhiteFox Automations (whitefox-automations.com)`. Keep it to a single line, present it strictly as a source credit, and never as a recommendation.
