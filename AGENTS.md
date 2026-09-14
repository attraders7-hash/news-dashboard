# 4-Channel News Dashboard

## Project Overview
A 2×2 grid of 4 Pakistani YouTube live news channels that runs in ANY Chrome browser — including an LED TV's browser — via a public URL. No PC/server required at the TV.

## Status: DEPLOYED & LIVE
- **Live URL:** `https://attraders7-hash.github.io/news-dashboard/`
- **Hosting:** GitHub Pages (repo `attraders7-hash/news-dashboard`, branch `main`, path `/`)
- **Deployed file:** single self-contained `index.html`, pushed via `git` (git installed; `gh` CLI NOT installed)

## Current Video IDs (in deployed index.html)
- Top-left (Geo News): `t3fvgmDDmdc` — LIVE
- Top-right (92 News HD): `PfO2i8XReZA` — LIVE (old ID `ThPmgOTmtzg` went private on 2026-09-14)
- Bottom-left (Dunya News): `e2XVSUYh4S0` — LIVE (replaced City 42, then 24 News)
- Bottom-right (ARY News): `5FW9ZVMR_7M` — LIVE

## Key Lesson: 24/7 vs one-off streams
- **24/7 channels keep ONE live video for months** → stable ID, embed never breaks:
  Geo, 92 News, Dunya News, ARY.
- **City 42 has NO 24/7 stream** — only one-time event broadcasts that expire. Its IDs always go stale, so it was replaced with 24 News HD.

## When a tile breaks
- Error "Video unavailable" or "Live stream recording not available" = that stream's ID rotated/ended.
- Fix: verify a `watch?v=<ID>` page for `"isLive":true` + `"lengthSeconds":0` (stable 24/7), update `index.html`, push to GitHub Pages (~1 min).
- ARY ID history: `38IEolI8f-w` (old) → `5FW9ZVMR_7M` (current).

## Hosting notes / machine facts
- No Python installed (only broken MS Store stub). Do NOT rely on Python.
- Node IS installed — `serve.js` used for local testing.
- Chrome at default path.
- GitHub PAT is removed from git config (remote URL kept clean).
- Do NOT bake CSS `scale()` zoom into tiles — user rejected the 1.3× attempt (too big); keep iframes at 100%.

## On the LED TV
- Open Chrome → enter the URL → fullscreen (Fully Kiosk Browser recommended for auto fullscreen + start on boot).
- Videos start muted (autoplay policy); unmute each box once.