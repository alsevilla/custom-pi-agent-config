# Project Memory — Explicit Session Memory

Give every project a persistent, cross-session memory so a new session
reconstructs context instantly. Ships an always-on `.planning/` convention
(`STATE.md` + `PROJECT.md` + `ROADMAP.md` + `REQUIREMENTS.md`) plus a `docs/`
folder for plans/brainstorms/solutions.

> Lazy, dependency-free. Templates live in `templates/planning/`. The convention
> is a plain folder in the **project root**, not in this skill — so it survives
> uninstall and is readable by you and every agent.

---

## When to use

- Greenfield project bootstrap, or opening an existing project mid-work.
- Any session where you need to know "where does this project stand?" without
  re-reading everything.
- Handing off to another agent/session.

## The convention

```
<project root>/
  .planning/
    PROJECT.md      # static: vision, constraints, tech stack
    STATE.md        # live: current focus, decisions, blockers, next actions
    ROADMAP.md      # phased goals + task checkboxes
    REQUIREMENTS.md # functional + non-functional reqs
  docs/
    plans/          # implementation plans
    brainstorms/    # explored approaches + trade-offs
    solutions/      # ce-compound learnings (feed from ce-compound)
```

- `.planning/` is the project's memory. **Never delete it.**
- `STATE.md` is the only file agents write every session. Everything else is
  written once (or updated when scope changes).
- `docs/solutions/` is where `ce-compound` drops learnings — same folder keeps
  memory and learnings adjacent.

## Commands / flow

### `project-memory:init` — create the memory for a project
1. Check if `.planning/STATE.md` already exists. If yes, resume from it
   (read Current Focus + Decisions + Next Actions) — do not overwrite.
2. If not, copy the templates into `<project root>/.planning/`:
   - `PROJECT.md` → fill Vision / Constraints / Tech Stack with the user.
   - `STATE.md` → leave as the initialized template.
   - `ROADMAP.md` / `REQUIREMENTS.md` → fill during `discuss`/`plan`.
3. Create empty `docs/plans/`, `docs/brainstorms/`, `docs/solutions/`.

```bash
# from project root
cp ~/.pi/agent/skills/project-memory/templates/planning/*.md .planning/
mkdir -p docs/plans docs/brainstorms docs/solutions
```

### Every session — read then write
- **Read** `.planning/STATE.md` first thing (Current Focus, Next Actions).
- **Append** a decision row to the Decisions table whenever a non-trivial
  decision is made.
- **Update** Current Focus + Last Updated when starting new work.
- **Update** Next Actions when the focus shifts.

### `project-memory:note` — quick decision capture
Append one row to `.planning/STATE.md` Decisions table:
`| {DATE} | {decision} | {rationale} |`

### Resume a session
Read `.planning/STATE.md` → read latest `docs/plans/` → state the current focus
and next action out loud before starting.

---

## Feeding the rest of the stack

- **Serena** — Serena memory is *agent/project how-to knowledge*; `.planning/` is
  *live project state*. Keep both: Serena for "how to work here", STATE.md for
  "what are we doing right now".
- **ce-compound** — point its `docs/solutions/` output at
  `<project>/.planning/../docs/solutions/` so learnings live next to state.
- **graphify** — index `.planning/` + `docs/` so semantic search covers the
  project's own memory, not just code.

## Guardrails

- Do not rewrite STATE.md — append/update in place. Rewrites lose history.
- Do not commit `.planning/STATE.md` secrets; it is plain text the whole team
  can read.
- One memory per project root. Nested `.planning/` dirs are ignored.
