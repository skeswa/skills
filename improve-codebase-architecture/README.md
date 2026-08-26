# improve-codebase-architecture

Scans a codebase for **deepening opportunities** — refactors that turn shallow modules into deep ones — presents them as a self-contained HTML report (Tailwind + Mermaid, with before/after diagrams per candidate), then grills you through whichever candidate you pick.

`disable-model-invocation: true`, so it only fires when you ask for it by name.

## Origin

Copied verbatim from [Matt Pocock's `skills` repo](https://github.com/mattpocock/skills) — specifically [`skills/engineering/improve-codebase-architecture`](https://github.com/mattpocock/skills/tree/main/skills/engineering/improve-codebase-architecture). Includes `SKILL.md` plus the linked reference `HTML-REPORT.md`. The upstream `agents/openai.yaml` is Codex-only metadata and was left behind.

## Dependencies

`SKILL.md` calls the Skill tool with three of Matt's other skills, all of which live in this repo:

- [`codebase-design`](../codebase-design) — the architecture vocabulary (module, interface, depth, seam, adapter, leverage, locality) the report is written in, plus the design-it-twice pattern
- [`grilling`](../grilling) — the decision-tree interrogation loop in step 3 (this repo's [`grill-me`](../grill-me) is the sibling entry-point skill, not the same one)
- [`domain-modeling`](../domain-modeling) — keeps `CONTEXT.md` and `docs/adr/` current as decisions land

None of the three depend on anything further, so that's the whole graph. The skill also expects a project domain glossary at `CONTEXT.md` and ADRs under `docs/adr/`, both created lazily by `domain-modeling`.
