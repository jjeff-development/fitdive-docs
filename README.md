# fitdive

Public site + docs for [FitDive](https://fitdive.app) — Garmin dive `.fit` → MySSI logbook, on iOS.

Plain static HTML, served via GitHub Pages. No build step.

- `index.html` — overview, pricing, App Store description
- `docs.html` — docs table of contents
- `setup.html` — getting-started setup guide
- `using.html` — tour of every screen in the app
- `garmin-import.html` — how the bulk Garmin Connect history import works
- `dive-matching.html` — how a Garmin dive is checked against your MySSI logbook, including the timezone caveat
- `find-dive-site.html` — how to find a fallback dive-site ID
- `privacy.html` — Privacy Policy (App Store submission URL)
- `support.html` — bug reporting + known-issue status
- `status.txt` — the app's live status check (see below)
- `CNAME` — custom domain (`fitdive.app`)

To edit: change the file directly, commit, push to `main`. Pages redeploys automatically.

## status.txt

The app fetches `https://fitdive.app/status.txt` before a bug report is submitted (`mobile/src/services/statusMessage.ts`) and shows a banner if there's a known issue. First line is either the literal `OK` (no banner shown) or the message to display. Edit it here on GitHub, or with the "edit on GitHub" link on the [Support page](https://fitdive.app/support.html) — no local clone needed for a quick status update.

## assets/showcase.json

**Consumed by an external site** — the JJeff Development LLC business site
(`jjeff.app`, separate repo at `../website`) `fetch()`s this file at
`https://fitdive.app/assets/showcase.json` to render its FitDive project
card, so it always shows current copy without needing its own repo touched.
Keep the existing keys (`status`, `name`, `description`, `url`, `image`,
`imageAlt`) intact when editing — the website's JS reads them by name and
silently falls back to its own hardcoded card if a key is missing or the
fetch fails, so a bad edit here degrades quietly rather than breaking
jjeff.app, but the field names still need to stay stable for the sync to
actually do anything.

App source lives in the [garmin2ssi_app](https://github.com/jjeff07/garmin2ssi_app) repo (`mobile/`).
