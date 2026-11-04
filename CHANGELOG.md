# Changelog: amsa (public demo)

## 1.1.0 (2026-11-03)
- **Display settings** (round button, bottom right), modelled on Apple's System Settings → Displays:
  - **Appearance: Auto / Light / Dark.** Auto follows the system Dark Mode (`prefers-color-scheme`) and switches live when the system does; Light or Dark overrides it for this site only. `theme-color` and `color-scheme` meta tags follow, so Safari's toolbar and form controls match.
  - **Night Shift:** Schedule (Off / Custom, default 10:00 PM–7:00 AM like macOS), **Turn On Until Tomorrow** (stays on until 7:00 AM or the schedule's end; switching it off during the schedule keeps it off until morning), and a **Less Warm–More Warm** slider. It's a warm overlay that never blocks clicks, fades in gently (instantly with Reduce Motion), and is hidden when printing.
  - Settings stay in this browser only and fall back gracefully when storage is blocked.
- Fixed: the live panel showed "NaN" viewers since X and Threads were added (their starting counts were missing). Missing platforms now count as 0.

## 1.0.1 (2026-11-03)
- supabase-js updated 2.45.4 → 2.118.0 (pinned; released 2026-10-15). Tested against the real library: waitlist RPC, demo events and backoffice login all work unchanged.

## 1.0.0 (2026-11-01)
- First public release, built from the AMSA Creator Console prototype v0.2.
- Screens: Analytics (incl. live panel), Go live (multistream relay config), Feed, My channel, Connections, and the new Join the beta screen.
- Platforms: YouTube, TikTok, Twitch, Facebook, Instagram, Kick, X, Threads, AMSA channel.
- Connected to Supabase: anonymous demo events, feedback and waitlist (insert-only, no reads).
- Offline outbox: failed sends are kept in the browser for up to 14 days and re-sent automatically.
- The Supabase client is stateless so it can never pick up a backoffice login on the same `djedyed.github.io` origin.
- No data export in the public demo by design; exports live in `amsaabo`.
