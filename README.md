# AMSA · All Media Streaming App (public demo)

One console for every streaming platform: go live everywhere at once, see one merged feed, and read unified analytics across YouTube, TikTok, Twitch, Facebook, Instagram, Kick, X, Threads and your own AMSA channel.

This repo is the **public demo**. Share it with anyone. The private operator backend lives in `djedyed/amsaabo`.

| | `amsa` (this repo) | `amsaabo` (private) |
|---|---|---|
| Who | Fans, creators, partners, investors | You and your admins |
| Data | Illustrative sample data | Real numbers from Supabase |
| Can | Explore, simulate a stream, join the waitlist, leave feedback | Analytics, live history, explorer, waitlist, brand-deal CRM, imports, exports, admin roles |
| Exports | None | All CSV exports + printable report |

## Display settings (Dark Mode + Night Shift)

- **Display settings** (round button, bottom right), modelled on Apple's System Settings → Displays:
  - **Appearance: Auto / Light / Dark.** Auto follows the system Dark Mode (`prefers-color-scheme`) and switches live when the system does; Light or Dark overrides it for this site only. `theme-color` and `color-scheme` meta tags follow, so Safari's toolbar and form controls match.
  - **Night Shift:** Schedule (Off / Custom, default 10:00 PM–7:00 AM like macOS), **Turn On Until Tomorrow** (stays on until 7:00 AM or the schedule's end; switching it off during the schedule keeps it off until morning), and a **Less Warm–More Warm** slider. It's a warm overlay that never blocks clicks, fades in gently (instantly with Reduce Motion), and is hidden when printing.
  - Settings stay in this browser only and fall back gracefully when storage is blocked.

## What the demo sends to Supabase

Only three things, all insert-only (it can never read anything back):

- `demo_events`: anonymous usage (which screens people open, simulated streams). A random per-browser id, no personal data.
- `feedback`: the rating and note from "Join the beta".
- `waitlist`: email, role, platforms and city, through the `join_waitlist` function. Only admins can read it.

If the connection drops, submissions wait in the browser and send automatically later.

## Hosting (GitHub Pages)

1. Upload `index.html` and this README to the repo root.
2. Settings → Pages → Deploy from branch → `main` / root.
3. It will be live at `https://djedyed.github.io/amsa/`.

The Supabase URL and the public anon key are already set near the bottom of `index.html`. The anon key is meant to be public: permissions come from Row Level Security.

## Version

See `CHANGELOG.md`. The version shows in the sidebar and in `<meta name="app-version">`.
