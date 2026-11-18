# University Physics Learning App

Offline-first installable web app (PWA). No build step, no dependencies.

## Publish on GitHub Pages
1. Create a repo and upload everything in this folder to the repo root.
2. Settings > Pages > Deploy from branch > `main` / root.
3. Open the Pages URL once while online, then use "Install app" / "Add to Home Screen".
After that it runs fully offline.

## How it works
- Database: IndexedDB in the browser (content, users, results, activity responses).
- Login: usernames and passwords hashed with PBKDF2 (Web Crypto). The first account created becomes the admin.
- Offline: `sw.js` caches the app files. When you change any file, bump `C="physics-v1"` in `sw.js` so installed copies update.

## Limits
- Each device has its own database. Admin and students only share data on the same device, or by Export/Import in Admin > Settings.
- GitHub Pages is static hosting, so there is no server. Cross-device sync would need a real server (e.g. Supabase or a Node/SQLite API) and would then need internet.
