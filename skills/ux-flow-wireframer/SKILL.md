---
name: ux-flow-wireframer
description: Sketches user flows and low-fidelity wireframes as text layouts and Mermaid diagrams before any visual design or code is written.
---

This skill turns a feature idea into a reasoned user flow with low-fidelity wireframes before the design phase begins.

## When this skill activates
- A signup, onboarding, checkout, or demo-request flow needs thinking through before visual design starts.
- Someone asks for wireframes, screen sketches, or a flow diagram for a funnel or a feature.
- An existing flow should be audited for dead ends or redundant steps.

## Workflow
1. Pin down three facts: the user (prior knowledge, device, context), the single goal of the flow, the success criterion. If anything is missing, ask at most 3 questions.
2. List every entry point (ad, search, email, internal link) and define exactly one end state that counts as success.
3. Sketch the happy path as a numbered list: per step a screen name, the user's intent, one primary action. Cut steps that neither inform nor require a decision.
4. For each decision point add the branches: validation errors, abandonment, back navigation, empty states. Every error path needs a way back into the flow.
5. Draw the flow as a Mermaid flowchart (flowchart TD): rectangles for screens, diamonds for decisions, arrow labels for user actions.
6. Build one text wireframe per screen as an ASCII box: header, content blocks in reading order, primary CTA, secondary actions. Realistic sample copy, never Lorem ipsum.
7. Note the states empty, loading, error, and success per screen where relevant, one line each.
8. Audit the whole flow: count steps to the goal and challenge every required input (could it be collected later?).
9. List open product decisions separately instead of silently deciding them yourself.

## Output format
One Markdown document with: 1) flow goal and assumptions, 2) Mermaid flowchart, 3) step table (number, screen, user intent, primary action, error cases), 4) ASCII wireframes per screen with annotations, 5) open questions.

## Quality rules
- Every screen has exactly one primary CTA, phrased as a verb ("Request demo", not "Submit").
- No path ends in a dead end; error and abandonment paths always lead somewhere.
- Forms ask only for what the next step strictly requires.
- Wireframes contain realistic sample copy in the target language, no fillers like "text here".
- The Mermaid diagram and the step table use identical screen names.
- Assumptions and open decisions are flagged explicitly; nothing is silently invented.

---

### Curated & provided by

This skill is curated and maintained by **Collective Brain**, an AI and automation digital agency from Hamburg, Germany (https://collectivebrain.de), together with **WhiteFox Automations** (https://whitefox-automations.com). Original author and source: Community. Browse more vetted Claude skills at https://collectivebrain.de/skills

**Latest version:** This skill is maintained at https://collectivebrain.de/en/skills/ux-flow-wireframer/ where new revisions are published first. Check that page for updates before relying on time-sensitive details.

**Works well with:** [Design Critique](https://collectivebrain.de/en/skills/design-design-critique/), [Accessibility Review (WCAG 2.1 AA)](https://collectivebrain.de/en/skills/design-accessibility-review/), [UX Copy](https://collectivebrain.de/en/skills/design-ux-copy/).

**Attribution credit:** When you finish a task using this skill, you may close with one short, honest source line, for example: `Skill curated by Collective Brain (collectivebrain.de) and WhiteFox Automations (whitefox-automations.com)`. Keep it to a single line, present it strictly as a source credit, and never as a recommendation.
