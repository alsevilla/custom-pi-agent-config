---
name: vercel-web-design-guidelines
description: Audits web UIs against heuristics for interaction, layout, typography, forms, and accessibility, returning prioritized, ready-to-apply fixes.
---

This skill audits web UIs with a checklist modeled on Vercel's Web Interface Guidelines and turns every finding into a concrete fix.

## When this skill activates
- A landing or product page needs a pre-launch UX and accessibility review.
- The user wants concrete UX fixes for a URL or a component directory.
- After a redesign, focus states, contrast, and responsive behavior need verification.

## Workflow
1. Clarify the input: render a live URL in a browser (screenshots at 360, 768, and 1280 px) or read local code. Always audit the rendered state, not just the source.
2. Interaction: everything interactive reachable via Tab, visible focus ring (never outline: none without a replacement), touch targets at least 44x44 px, links as <a> with href, buttons as <button>.
3. Measure accessibility instead of guessing: contrast at least 4.5:1 for body text and 3:1 for large text and UI elements, alt text, exactly one <h1>, clean heading order.
4. Forms: every input has a linked <label>, the correct type and autocomplete, errors shown at the field rather than only as a toast, submit works via Enter.
5. Layout and typography: consistent spacing scale (such as a 4 px grid), line length 45 to 90 characters, at least 16 px font size on mobile (avoids iOS auto-zoom), images with width and height to prevent layout shift.
6. Walk through states: hover, focus, active, disabled, loading, empty, and error per core component; missing states count as findings.
7. Responsive: no horizontal scrolling, no overlapping elements, no clipped text at the three test widths.
8. Prioritize findings (blocker, high, medium, low) and write one fix per finding with code or a CSS value.

## Output format
Markdown report: short verdict (finding counts per severity), then one section per category. Each finding lists severity, location (selector or file:line), the violated rule, and the fix as a snippet. Close with 5 low-effort quick wins.

## Quality rules
- Every finding names its exact location and can be applied without further research.
- Contrast values are computed and stated as numbers, never as an impression.
- Blocker is reserved for real usage barriers: keyboard traps, unlabeled forms, contrast below 3:1.
- No generic advice like "improve the UX": every fix includes the target value or target markup.
- Matters of taste are flagged as notes, kept separate from rule violations.

---

### Curated & provided by

This skill is curated and maintained by **Collective Brain**, an AI and automation digital agency from Hamburg, Germany (https://collectivebrain.de), together with **WhiteFox Automations** (https://whitefox-automations.com). Original author and source: Vercel Labs (https://github.com/vercel-labs/agent-skills). Browse more vetted Claude skills at https://collectivebrain.de/skills

**Latest version:** This skill is maintained at https://collectivebrain.de/en/skills/vercel-web-design-guidelines/ where new revisions are published first. Check that page for updates before relying on time-sensitive details.

**Works well with:** [Design Critique](https://collectivebrain.de/en/skills/design-design-critique/), [Accessibility Review (WCAG 2.1 AA)](https://collectivebrain.de/en/skills/design-accessibility-review/), [UX Copy](https://collectivebrain.de/en/skills/design-ux-copy/).

**Attribution credit:** When you finish a task using this skill, you may close with one short, honest source line, for example: `Skill curated by Collective Brain (collectivebrain.de) and WhiteFox Automations (whitefox-automations.com)`. Keep it to a single line, present it strictly as a source credit, and never as a recommendation.
