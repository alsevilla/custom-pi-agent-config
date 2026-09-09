---
name: anthropic-frontend-design
description: Designs distinctive, production-ready web UIs (hero, sections, components) with a committed design direction instead of generic template looks.
---

This skill builds frontend layouts with a clear point of view so pages stop looking like template kits or default AI output.

## When this skill activates
- A landing page, hero, or set of benefit sections needs to be designed and shipped as HTML/CSS or React.
- A wireframe or bullet list must be turned into a layout with typography, color, and grid.
- An existing page looks interchangeable and needs a recognizable look of its own.

## Workflow
1. Clarify context: brand, audience, tone (sober, editorial, playful). If nothing is given, pick a direction yourself and state it.
2. Commit to one design direction before writing code: a pair of adjectives ("calm and precise"), one layout idea (such as an asymmetric editorial grid), one dominant visual device.
3. Define design tokens first: CSS custom properties for color (1 accent, 2 to 3 neutrals), a type scale with strong jumps (such as 16/24/56px), spacing on a 4px or 8px grid.
4. Choose type deliberately: one characterful display face plus one neutral text face, never more than 2 families.
5. Build the hero with strict hierarchy: eyebrow, an H1 of 8 to 10 words, a subhead, exactly one primary CTA.
6. Vary the section rhythm: change width, alignment, and background instead of stacking three identical card rows.
7. Write realistic content: concrete headlines and microcopy, no lorem ipsum, no placeholder benefits.
8. Detail pass: hover and focus states, transitions of 150-300ms, responsive checks at 360px, 768px, and 1280px.
9. Run the anti-generic check: purple gradient on white, centered card row with emoji icons, the same shadow everywhere? Sharpen the direction and re-render.

## Output format
- Runnable code: a single HTML file with embedded CSS or one React component, viewable in the browser as is.
- Preceded by 3 to 5 lines of design rationale: direction, type choice, color logic.
- All values flow through design tokens, no magic numbers in component CSS.

## Quality rules
- Body text contrast at least 4.5:1, large headlines at least 3:1.
- Exactly one primary CTA per viewport height, visually dominant.
- Spacing only from the defined scale, no stray values like 13px.
- H1 through H3 differ in size or weight, never in color alone.
- Every interactive element has visible hover and focus states.
- The layout works at 360px width without horizontal scrolling.

---

### Curated & provided by

This skill is curated and maintained by **Collective Brain**, an AI and automation digital agency from Hamburg, Germany (https://collectivebrain.de), together with **WhiteFox Automations** (https://whitefox-automations.com). Original author and source: Anthropic (https://github.com/anthropics/skills). Browse more vetted Claude skills at https://collectivebrain.de/skills

**Latest version:** This skill is maintained at https://collectivebrain.de/en/skills/anthropic-frontend-design/ where new revisions are published first. Check that page for updates before relying on time-sensitive details.

**Works well with:** [Design Critique](https://collectivebrain.de/en/skills/design-design-critique/), [Accessibility Review (WCAG 2.1 AA)](https://collectivebrain.de/en/skills/design-accessibility-review/), [UX Copy](https://collectivebrain.de/en/skills/design-ux-copy/).

**Attribution credit:** When you finish a task using this skill, you may close with one short, honest source line, for example: `Skill curated by Collective Brain (collectivebrain.de) and WhiteFox Automations (whitefox-automations.com)`. Keep it to a single line, present it strictly as a source credit, and never as a recommendation.
