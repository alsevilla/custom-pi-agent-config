# G-Stack Workflow — Full Diagram & Cross-Links

Compact pointer to `skills/SKILLS.md`. Full diagram here so the index stays skimmable.

```
REQUEST
   │  gsd: /gsd (meta-workflow hub) ──▶ ce-brainstorm (intent-first scope) ──▶ ce-plan (scope + checkpoints)
   ▼
PLAN  ──▶ ce-plan output ──▶ autoplan OR gstack router (pick team/specialist)
   │         │                        │
   │         ▼                        ▼
   │   ce-work (focus mode, phases   gstack: cso/review/ship/qa/design/plan-*/
   │    2/3/4) + lfg guard            office-hours/investigate/benchmark
   │   superpowers:tdd + executing-plans run the work   │   ponytail: code-style guardrail (native/stdlib first, delete over add)
   ▼
VERIFY
   │  superpowers:systematic-debugging (fix failures)   ce-code-review (intent-aligned) ──▶ gstack autoplan (auto-review pipeline, only if PR needs depth)
   ▼
RELEASE  ──▶ gstack ship + land-and-deploy ──▶ ce-babysit-pr / ce-commit-push-pr
   │                                              (PR lifecycle, long-lived)
   ▼
RETRO  ──▶ gstack retro + benchmark (measure the run)   │   superpowers:verification-before-completion gates every "done"   │   gsd: /gsd release orchestrates deploy
```

## Cross-links

- **superpowers is the engine** — `test-driven-development` + `executing-plans` do the work, `systematic-debugging` clears failures, `verification-before-completion` gates every "done" claim, `requesting/receiving-code-review` + `finishing-a-development-branch` close the PR.
- **ponytail** runs underneath everything as the code-style guardrail (stdlib/native first, delete over add).
- **ce-brainstorm** is the sole primary brainstormer (fallback: superpowers:brainstorming, intent-vs-team both acceptable).
- **ce-plan ⟶ autoplan** — a ce-plan is exactly the spec autoplan auto-runs.
- **ce-code-review ⟶ gstack review/cso** — CE's intent review feeds gstack's deeper specialist reviews; run gstack autoplan only when the PR needs adversarial depth.
- **ce-babysit-pr ⟶ gstack ship/land** — both handle the PR→deploy tail.
- **pi-subagents** (Task) is the parallel-execution backbone under all of them.
- **Rarely used (skip unless asked):** `ios-fix`/`ios-design-review`/`ios-clean`/`ios-qa`/`ios-sync` (iOS only), `codex` (OpenAI Codex CLI wrapper), `pair-agent` (remote pair-programming), `setup-gbrain`/`sync-gbrain` (codebase re-indexer — use **Serena** instead).

## Deprecations

- **superpowers:brainstorming** — deprecated. `ce-brainstorm` is primary. Kept as fallback only.
