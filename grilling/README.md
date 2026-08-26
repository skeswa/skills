# grilling

The interrogation loop itself: map the plan as a design tree, ask the whole **frontier** (every decision whose prerequisites are settled) in one numbered round with a recommended answer each, wait, recompute, repeat until the frontier is empty. Facts are Claude's job — it dispatches sub-agents rather than asking you to look things up. Decisions are yours.

## Origin

Copied verbatim from [Matt Pocock's `skills` repo](https://github.com/mattpocock/skills) — specifically [`skills/productivity/grilling`](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling).

## Relationship to `grill-me`

Upstream has since split the two: [`grill-me`](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) is now a one-line entry point that calls `grilling`, so other skills can reuse the loop without inheriting the trigger phrases. This repo's [`grill-me`](../grill-me) is still the older self-contained copy, which means the loop currently exists twice with a slightly different round format. Collapsing `grill-me` down to the upstream one-liner would deduplicate it.

## Used by

- [`improve-codebase-architecture`](../improve-codebase-architecture) — step 3, once you've picked a candidate
