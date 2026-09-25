# herald-extension — engineering log

Newest entry on top. Format and rules: `kv-10/herald-runner/HANDOFF.md` §0. Engineers: Claude, Codex. Owner: Ketan.
Rules for this repo: ship small fixes WITHOUT a version bump (Ketan's rule — a past bump broke things). Pushes to `popup.js`, `background.js`, `popup.html`, `manifest.json`, `gmail.js` or `vercel.json` rebuild the XPI. Firefox won't auto-update without a bump, so users reinstall from petvalu-bot.vercel.app/petvalu-bot.xpi.

## 2026-09-25 15:50 ET — Claude — Added this log
- Branch / commit: main (this commit)
- What: `LOG.md` (this file).
- Why: two-engineer logging rule from Ketan.
- Effect: documentation only. `LOG.md` isn't a build-trigger path, so the XPI doesn't rebuild.

## 2026-09-25 — Claude — Fixed substitute items being flagged instead of entered (still v2.2.10)
- Branch / commit: main @ fa0ad9a (two pushes that day)
- What: `popup.js` `findSubRow()`:
  1. It matches on column id `subst_item_No` (the portal's real id), falling back to `substituted_item` / `item_no`.
  2. It returns the grid's center row piece (same `row-id`) instead of the pinned-left piece, which has no Qty cell.
- Why: substitute items were always flagged. The old code looked for a column id that doesn't exist, and then acted on the wrong half of the row.
- Effect: the same fix was proven in the cloud runner. 39012 entered via substitute 1000120 on store 2356. No version bump, so a manual XPI reinstall is needed.
- Risks / follow-ups: extension icons are still broken (cosmetic, back burner).
