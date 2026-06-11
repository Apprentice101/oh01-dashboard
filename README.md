# OH-01 Voting Procedures Dashboard

Built from `voting-dashboards-source` repo, district config `client/src/configs/oh-01.ts`.

## District profile
- **State**: Ohio
- **Counties**: Hamilton (Cincinnati) + Warren
- **2026 race**: Greg Landsman (D, incumbent — 67.9% in May 5 primary) vs Eric Conroy (R, Trump-endorsed, 71.88% primary) + John Hancock (L). SJR 10 voter ID amendment on same ballot.
- **Next key date**: Nov 3, 2026 (general)
- **Cook PVI / rating**: Lean D
- **Election admin**: Ohio SOS (Frank LaRose)

## Data inventory
- 12 sources verified (state SOS + county election offices + nonpartisan journalism)
- 12 rules — all `needsReview: true, confidence: "unconfirmed"` (verify before publish)
- 15 election events on timeline
- 9 voter resources
- 6 news cards (last 90 days)
- 3 updates panel entries (initial-build inventory)
- 1 conflict logged: SB 293 absentee receipt deadline — statute says Election Day close; some Hamilton County BOE pages still reference old 4-day grace window

## Deploy to GitHub Pages

```bash
# In Apprentice101/oh01-dashboard repo:
git add .
git commit -m "Deploy OH-01 dashboard"
git push -u origin main
```

Enable GitHub Pages from main branch root in repo settings.

## Files
- `index.html` — entry point
- `snapshot.json` — district data (data layer)
- `assets/` — bundled JS/CSS

## QA status (2026-06-11)
- All rules and events marked `confidence: "unconfirmed"` — strict review required before public ship per user policy
- Zero console errors on smoke test
- Review Queue tile, district map, tab highlighting, Updates/Conflicts panels all rendering correctly (post-v2 fixes)

## Built from
- Source repo: https://github.com/Apprentice101/voting-dashboards-source
- Config file: `client/src/configs/oh-01.ts`
- Build command: `VITE_DISTRICT_ID=OH-01 npm run build:static`

## Title fix (2026-06-11 patch)
- Browser tab `<title>` now reads "OH-01 Voting Procedures Dashboard" (was generic/empty)
- `client/index.html` and `script/build-static.ts` updated so all future builds get the district title automatically
