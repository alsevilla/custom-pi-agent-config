# Global Instructions

## Lazy skills — read this first

Most skills are **not** loaded at session start. `~/.pi/agent/skills/SKILLS.md`
is the index. **Read it** before picking up any method/over-engineering skill:
it names the right skill and points to its real `SKILL.md`.

### Why
Pi loads every package's skills at startup. To keep a plain session light, the
`obra/superpowers` package was removed from the always-on `packages` list, so
its skills load **0** at startup. When a task needs them, read `SKILLS.md`,
then the one `SKILL.md` it points to. The same rule applies to the G-Stack
skills (GSD Core, compound-engineering, gstack) — they're lazy too.

### What stays loaded
- `ponytail` (persistent mode, already in the system prompt) — on by default.
- Built-in skills in `~/.pi/agent/skills/` (graphify, obsidian-*, json-canvas,
  defuddle) — auto-discovered.
- G-Stack extensions loaded at startup: gsd-core (`/gsd`), compound (`ce-*`),
  gstack (router + specialists), pi-subagents, pi-ask-user.

### What is lazy (read `SKILLS.md`, then load the one you need)
- **superpowers** system (brainstorming, writing-plans, TDD, systematic-debugging,
  verification, code-review…) — on demand via `SKILLS.md`.
- **GSD Core** commands (`/gsd-new-project`, `/gsd-onboard`, `gsd-spec`…) — on
  demand; `/gsd` is the hub for the rest.
- **compound-engineering** (`ce-brainstorm`, `ce-plan`, `ce-work`, `ce-code-review`,…)
  — on demand via `SKILLS.md`.
- **gstack** (`gstack` router + autoplan/cso/review/ship/qa/…) — on demand.
- Ponytail sub-skills (ponytail-review, -audit, -debt, -gain, -help) — loaded
  on demand via `SKILLS.md`.

### Workflow
A task needs a method → read `SKILLS.md` → read the matching `SKILL.md` →
proceed. The index lists skill, when-to-use, and path for every system.

### Config (for reference)
- Always-on packages: `~/.pi/agent/settings.json` → `packages`.
- Remove a package from that list to make it fully lazy.
