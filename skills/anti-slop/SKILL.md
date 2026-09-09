# Anti-Slop Rule — One Checklist, Every Surface

Write like a competent human engineer, not a chatbot. Every word and every line
must earn its place. **This is the single consolidated anti-AI-slop reference.**
It is not a new skill — it is the shared checklist that three of ours already
enforce, unified so an agent can grep one file:

- **ponytail** (code style — always on every response)
- **design-taste-frontend** / **redesign-existing-projects** / **design-design-critique** (UI taste)
- **ponytail-review** / **ponytail-audit** (the review pass that applies this)

> This rule does not replace them — it names what they all check. When a task
> matches, follow the primary skill; use this as the checklist it applies.

---

## Code — Keep It Normal

1. **No unnecessary abstraction** — no wrapping a single function in a class, no factory for one type, no layer "for future flexibility." (ponytail)
2. **No premature generalization** — solve the problem in front of you; build a framework only when three callers prove it.
3. **No filler comments** — `// set the value` above `setValue(x)`. Comments explain WHY, never WHAT. (ponytail)
4. **No redundant names** — `userUserName`. `username` is fine.
5. **No over-documenting obvious code** — a getter needs a docblock only with side effects.
6. **No unnecessary async** — if nothing awaits, it is not async.
7. **No empty catch** — handle the error or let it propagate.
8. **No magic numbers** — `retries > 3` → `MAX_RETRIES`.
9. **No deep nesting** — more than 3 indentation levels → extract a function.
10. **No god functions** — >40 lines suspicious, >80 wrong.
11. **No boolean-parameter APIs** — `createUser(true, false, true)` → options object.
12. **No string enums** — use enum / union type for a known set.
13. **Prefer const / immutable** — `const` over `let`; immutable data by default.
14. **No barrel imports that pull everything** — import only what is used.
15. **No circular dependencies** — restructure.
16. **No console.log in production** — use a logger.
17. **No hardcoded URLs/paths** — env vars or config.
18. **No commented-out code** — delete it; git remembers.
19. **No orphan TODOs** — `TODO(ticket-123)` or delete.
20. **No copy-paste duplication** — pasted twice → extract.
21. **No implicit coercion** — `===` not `==`.
22. **No mixed abstraction levels** — a function does not mix HTTP calls with string formatting.
23. **No unused imports/variables** — noise. Delete.
24. **No overly clever one-liners** — takes >5s to read → split it. (ponytail)
25. **No util grab-bag files** — `utils.ts` that grows forever is a smell; group by domain.
26. **No test-only code in production** — belongs in test files.
27. **No excessive mocking** — mock at boundaries, not everything.

---

## UI — Taste

- **No AI purple glow.** No automatic blue/purple button glows, no random neon gradients. Neutral base (Zinc / Slate / Stone), one high-contrast accent. (design-taste — "THE LILA RULE")
- **No neon, no rainbow gradients, no saturated primaries on large surfaces.**
- **One accent color** — sparingly, for CTAs and focus states.
- **WCAG AA minimum** — 4.5:1 text, 3:1 large text/UI.
- **No pure black on pure white** — off-black on off-white.
- **Dark mode is intentional** — never just invert colors.
- **Semantic colors** — error=red, warning=amber, success=green, info=blue. Don't deviate.
- **Opacity over one-off colors** — palette variants, not new hues.
- **No templated layouts** — infer direction from the brief before touching code.
- **Check `package.json` before importing any component library** — never assume it exists.

---

## Hard No — Banned Phrases (never in code, comments, commits, PRs, or chat)

"I'd be happy to", "Let me", "Great question", "Certainly", "Absolutely", "Of course",
"I'll go ahead and", "Let's dive in", "Here's what I've done", "I've taken the liberty",
"As an AI", "I don't have personal opinions, but", "That's a great point",
"To be honest", "In my experience" (you have no experience), "I think" (state facts/uncertainties directly),
"Basically", "Simply", "Just" (minimizer — drop it), "Obviously", "It's worth noting",
"Leverage" (say "use"), "Utilize" (say "use"), "Robust" (say what makes it strong).

---

## Communication

- Direct statements, not hedged suggestions. Active voice, not passive.
- Specific claims, not vague assertions. Short sentences. No walls of text.
- When uncertain, say "I am not sure" — no filler hedging.
- Error messages: say what went wrong, what the user can do, nothing else.

---

## Where each rule lives (so this stays a checklist, not a duplicate)

- **Code rules 1–27 → ponytail** (always-on guardrail). `ponytail-review` / `ponytail-audit` apply them.
- **UI rules → design-taste-frontend** / **redesign-existing-projects** / **design-design-critique**.
- **Hard No + Communication → every response** (ponytail is on by default; this names the banned phrases explicitly).
