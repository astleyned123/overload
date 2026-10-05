# Overload — Lift Tracker

A progressive overload tracker that runs on your Android phone as a home-screen app.
All your data stays on your phone.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole app (screens, progression logic, exercise library, statistics) |
| `manifest.webmanifest` | Lets Android install it as an app with an icon |
| `sw.js` | Makes it work offline at the gym |
| `icons/` | App icons |

## Put it on your phone (one-off, ~10 minutes)

The app needs to live at a web address so Chrome can install it. GitHub Pages does this for free.

**1. Create the repository**
1. On a computer, go to [github.com](https://github.com) and sign in.
2. Click the **+** (top right) → **New repository**.
3. Name it `overload`, set it to **Public**, and click **Create repository**.

**2. Upload the files**
1. On the new repo page, click **uploading an existing file**.
2. Drag in **everything inside** this folder: `index.html`, `manifest.webmanifest`, `sw.js`, `README.md`, and the `icons` folder.
   Drag the files themselves, not the folder that contains them.
3. Click **Commit changes**.

**3. Turn on GitHub Pages**
1. In the repo, go to **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment** → **Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)** → **Save**.
4. Wait 1–2 minutes and refresh. Your link appears at the top:
   `https://YOUR-USERNAME.github.io/overload/`

**4. Install on your phone**
1. Open that link in **Chrome** on your Android.
2. Tap the **⋮** menu → **Add to home screen** (or **Install app**) → **Install**.
3. Open it from your home screen. It now works offline.

> The repo is public, but it only contains the app's code. Your workouts are stored on your phone and never uploaded.

## How the progression works (double progression)

Each exercise has a rep range, e.g. 3 × 6–10.

- **Every set hits the top of the range** → next session the weight goes up by the smallest jump
  (barbell 1.25 kg; dumbbells, machines and cables 2.5 kg). Reps reset to the bottom of the range.
- **Within the range** → same weight next time. The app sets each set's target to one more rep than last time.
- **Any set below the bottom of the range** → same weight, try again.
  If it happens **two sessions in a row**, the app deloads by 10% (rounded down to your smallest jump).

Tip: when logging, tapping ✓ on an empty set records the "aim" number. Type the real reps first if you got fewer.

## Backups

Settings → **Back up now** → **Share to Google Drive**. The app reminds you every 7 days.
To restore on a new phone: install the app, then Settings → **Restore** → pick the backup file.

Clearing Chrome's site data, or uninstalling the app, deletes your history. Keep backups.

## Updating the app later

1. In `sw.js`, change `overload-v1.0.0` to a new number (e.g. `overload-v1.0.1`).
2. Upload the changed files to the repo (same **Add file → Upload files** page) and commit.
3. Open the app on your phone, close it, and open it again to get the new version. Your data is unaffected.
