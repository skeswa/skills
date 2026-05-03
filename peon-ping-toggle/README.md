# peon-ping-toggle

A user-invocable Claude Code skill that mutes/unmutes [peon-ping](https://github.com/PeonPing/peon-ping) sounds for the current session by shelling out to its `peon.sh --toggle` control.

## What is peon-ping?

[peon-ping](https://github.com/PeonPing/peon-ping) ([peonping.com](https://www.peonping.com)) plays Warcraft III Peon (and other game) voice lines when an AI coding agent finishes or needs your attention, so you don't have to babysit the terminal. It installs as a Claude Code hook at `~/.claude/hooks/peon-ping/peon.sh`.

## Why this skill exists

peon-ping ships its own `peon` CLI for toggling sound, but invoking it through a Claude Code skill means you can mute/unmute mid-session by typing `/peon-ping-toggle` instead of context-switching to a shell.

## Prerequisites

peon-ping must already be installed — the skill assumes `~/.claude/hooks/peon-ping/peon.sh` exists. See the [peon-ping install instructions](https://github.com/PeonPing/peon-ping#install).
