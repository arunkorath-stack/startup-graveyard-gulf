# Startup Graveyard — Gulf Edition

A single-file, dependency-free website: a forensic database of 100+ failed startups across 25 countries with a dedicated UAE wing, Case-of-the-Week classroom mode, dashboards, rebuild plans and an ideas directory.

Everything is in `index.html` (fonts load from Google Fonts; nothing else is fetched).

## Deploy to Render (free static site) — ~3 minutes

1. Create a new GitHub repository (e.g. `startup-graveyard-gulf`) and upload these three files to its root.
2. In Render: **New → Static Site → connect the repo**. Leave *Build Command* empty and set *Publish Directory* to `.` (`render.yaml` already says this, so Render will prefill it if you choose "Blueprint").
3. Click **Create Static Site**. Your URL will be `https://startup-graveyard-gulf.onrender.com` (or whatever name you pick).

## Or GitHub Pages — ~1 minute

Repository → **Settings → Pages → Source: Deploy from a branch → main / (root)**. URL: `https://<your-user>.github.io/startup-graveyard-gulf/`.

## Notes

- **Shared class storage.** On claude.ai the page uses the artifact's built-in database for shared submissions, loot counts and the quiz leaderboard. On Render/GitHub Pages that API does not exist, so the page automatically falls back to browser-only storage and shows "Shared storage unavailable here". The Export/Import JSON buttons still work for collecting a class's cases. If you want shared storage on the public site, the cleanest route is a small Supabase table (free tier) — the code is isolated in the `SHARED STORE` section of `index.html` and can be swapped in ~60 lines.
- **Updating.** Edit `index.html`, push, Render redeploys automatically.
- **Data.** UAE cases carry sources; most global entries are marked `~` approximate. Causes are collapsed to 9 standard categories; the original detail is kept.
