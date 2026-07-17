---
type: reference
tags: [repo/PROJECT_TEMPLATE]
up: "[[PROJECT_TEMPLATE]]"
---
# Planning

**Status:** Brief written for Fable to pick up (2026-07-17). Cameron
considers the concept itself straightforward — the open questions below are
about implementation approach, not whether this is worth doing.

## Problem

Setting up a new machine (or restoring a wiped one) means manually
reinstalling apps, redoing preferences, and re-finding the right key
directories from scratch, every time. No automation exists for this today.

## Scope

- **App installations** — the set of apps/tools Cameron reinstalls every
  time.
- **Preferences** — OS + app settings/dotfiles worth carrying over (shell
  profile, git config, editor settings, etc.).
- **Key directories** — re-establishing Projects, repos, and the Obsidian
  vault on the new machine.

## Vision

Ship as a standalone packaged tool — same bar as `StorageAnalyzer`'s own
goal ("native UI, no web UI; a real packaged installer/exe"), not a folder of
loose scripts Cameron has to remember to run in the right order.

## Open questions (the actual scope of this brief)

- **Inventory source.** Does it read a manifest Cameron maintains by hand, or
  try to snapshot an existing machine's actual installed state (e.g. a
  `winget export`, registry scan)?
- **Where config data lives between machines.** Checked into this repo
  (careful: some prefs/dotfiles may carry secrets), a private gist, cloud
  storage, or generated fresh from a template each run?
- **Overlap with `workforce`'s own setup scripts.** `workforce/setup-junctions.ps1`
  and `workforce/install.ps1` already link that repo's own skills/agents onto
  a new machine. Should ColdStart call into those, or is workforce a separate
  concern (workforce sets itself up; ColdStart handles everything else)?
- **Platform scope.** Windows-only (matches Cameron's current machines), or
  worth designing for portability?

## Current State

Just scaffolded (2026-07-17) from PROJECT_TEMPLATE. No code yet.

## Related

- `StorageAnalyzer` — sibling tool, same packaging bar.
- `workforce/setup-junctions.ps1`, `workforce/install.ps1` — existing,
  narrower prior art for "make a new machine usable."
- [[Repos/PROJECT_TEMPLATE/planning/PHASE_1|PHASE_1]]
- [[Repos/PROJECT_TEMPLATE/planning/TODO|TODO]]
- [[PROJECT_TEMPLATE]]
