# Attendance Register — Super Packaging

A self-contained attendance register (no backend, no server) for tracking daily
present/absent, time in/out with overtime, and monthly totals — for both
Company Workers and Contractor Workers. Installable as an app on any phone.

## Files in this folder

```
index.html            → the entire app (HTML + CSS + JS in one file)
manifest.json          → makes it installable as an app (name, icon, colors)
service-worker.js       → lets it open even with no signal, once installed
icons/
  icon-192.png          → app icon (Android home screen)
  icon-512.png           → app icon (larger, splash screens)
  icon-512-maskable.png   → adaptive icon for Android (safe-zone padded)
  apple-touch-icon.png    → app icon (iPhone home screen)
  favicon.png              → browser tab icon
```

Upload **all of these files, keeping the `icons` folder structure intact** —
if the icons folder isn't uploaded exactly as-is, the app will still work,
it'll just fall back to a generic icon.

## Deploy to GitHub Pages

1. Go to github.com, sign in to your account.
2. **New repository** → name it (e.g. `attendance-register`) → keep it
   **Public** → Create repository.
3. **Add file → Upload files** → drag in `index.html`, `manifest.json`,
   `service-worker.js`, and the whole `icons` folder. GitHub preserves the
   folder structure automatically.
4. Commit the files.
5. Go to **Settings → Pages**. Under "Build and deployment," set Source to
   **Deploy from a branch**, Branch = `main`, Folder = `/(root)`. Save.
6. Wait a minute, then refresh — it'll show your live link, something like:
   `https://<your-username>.github.io/attendance-register/`

## Sharing with your manager

Send him that link on WhatsApp. He opens it, taps his browser menu →
**Add to Home Screen**, and it behaves like a regular app icon from then on —
opens instantly, works offline, and everything he marks is saved on his phone.

At month-end he opens **Monthly Total** and taps **Share on WhatsApp** or
**Export PDF** to send you the report.

## Notes

- Data is stored locally on each device (localStorage) — there is no shared
  account or server. Each phone keeps its own independent copy.
- Updating the app later: just re-upload a changed `index.html` to the same
  repo. Everyone's saved attendance data stays untouched since it lives on
  their device, not in the file.
