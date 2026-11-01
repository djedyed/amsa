# Changelog: amsa (public demo)

## 1.0.0 (2026-11-01)
- First public release, built from the AMSA Creator Console prototype v0.2.
- Screens: Analytics (incl. live panel), Go live (multistream relay config), Feed, My channel, Connections, and the new Join the beta screen.
- Platforms: YouTube, TikTok, Twitch, Facebook, Instagram, Kick, X, Threads, AMSA channel.
- Connected to Supabase: anonymous demo events, feedback and waitlist (insert-only, no reads).
- Offline outbox: failed sends are kept in the browser for up to 14 days and re-sent automatically.
- The Supabase client is stateless so it can never pick up a backoffice login on the same `djedyed.github.io` origin.
- No data export in the public demo by design; exports live in `amsaabo`.
