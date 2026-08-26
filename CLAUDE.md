# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Personal collection of Claude Code Skills owned by the user (sandile.keswa@gmail.com). Some skills are original, some adapted from others. Reference: https://code.claude.com/docs/en/skills#where-skills-live

`~/.claude/skills` is a symlink to this repo, so any edit here is **live** for the running Claude Code session — no install/build/restart step. New skills appear after the next session start.

## Skill anatomy

One skill = one top-level directory containing a `SKILL.md`. The directory name must match the `name` frontmatter field. Frontmatter fields seen in this repo:

- `name` — kebab-case, matches the directory
- `description` — model-facing trigger text. Phrase it so Claude knows _when_ to invoke (include trigger phrases the user is likely to say, e.g. "grill me")
- `user_invocable: true` — opt-in to expose the skill as a `/<name>` slash command. Omit for skills that should only be model-triggered

Body below the frontmatter is the prompt Claude follows when the skill fires. Keep it imperative and short — these run inline in a real session.

## Conventions

- Author skills in second person ("Interview me…", "Run the following command…") — they are instructions to a future Claude, not docs about Claude.
- If a skill shells out to a hook or script, reference the absolute `~/.claude/...` path (see `peon-ping-toggle/SKILL.md`); the user's hooks live outside this repo.
- Validate a new skill by starting a fresh Claude Code session and either invoking it via `/<name>` (if `user_invocable`) or producing an utterance that matches its `description`.

## Tooling

This is a content repo, but it uses **[mise](https://mise.jdx.dev/)** to pin the toolchain (Node, via `mise.toml`) and to run tasks, **npm** for dependencies, and **[oxfmt](https://github.com/oxc-project/oxc)** for formatting Markdown/JSON. Run before committing:

```bash
mise run fmt       # → npx oxfmt ., formats per .oxfmtrc.json
```

First time in a fresh clone:

```bash
mise install       # installs the pinned Node
mise run install   # → npm ci
```

Use `npm` (not `pnpm`/`yarn`) for dependency changes so `package-lock.json` stays consistent, and add new commands as `[tasks.*]` entries in `mise.toml` rather than `scripts` in `package.json`.
