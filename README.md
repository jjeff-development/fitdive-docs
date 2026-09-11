# fitdive

Public site + docs for [FitDive](https://fitdive.app) — Garmin dive `.fit` → MySSI logbook, on iOS.

Plain static HTML, served via GitHub Pages. No build step.

- `index.html` — overview, pricing, App Store description
- `privacy.html` — Privacy Policy (App Store submission URL)
- `support.html` — bug reporting + known-issue status
- `status.txt` — the app's live status check (see below)
- `CNAME` — custom domain (`fitdive.app`)

To edit: change the file directly, commit, push to `main`. Pages redeploys automatically.

## status.txt

The app fetches `https://fitdive.app/status.txt` before a bug report is submitted (`mobile/src/services/statusMessage.ts`) and shows a banner if there's a known issue. First line is either the literal `OK` (no banner shown) or the message to display. Edit it here on GitHub, or with the "edit on GitHub" link on the [Support page](https://fitdive.app/support.html) — no local clone needed for a quick status update.

App source lives in the [garmin2ssi_app](https://github.com/jjeff07/garmin2ssi_app) repo (`mobile/`).
