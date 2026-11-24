# How to put LabLens on the internet (once) so it works offline forever

You only need the GitHub website. No coding, no downloads.

## What you have (6 files)
`index.html` · `manifest.json` · `sw.js` · `icon-192.png` · `icon-512.png` · `icon-maskable-512.png`

All six must be uploaded together, into the main folder (not inside another folder).

## Step 1. Create a repository
1. Go to github.com and sign in.
2. Tap **+** (top right) → **New repository**.
3. Name it `lablens`. Choose **Public**. Tap **Create repository**.

## Step 2. Upload the files
1. On the new empty repository page, tap **uploading an existing file**.
2. Drag in (or choose) all 6 files.
3. Scroll down and tap **Commit changes**.

## Step 3. Turn on the website
1. In the repository, tap **Settings** → **Pages** (left menu).
2. Under **Branch**, choose **main** and folder **/ (root)**. Tap **Save**.
3. Wait 1–2 minutes and refresh. A link appears at the top, like  
   `https://YOUR-USERNAME.github.io/lablens/`

## Step 4. Install it on a phone or computer (needs internet only this once)
- **Android (Chrome):** open the link → menu ⋮ → **Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open the link → Share button → **Add to Home Screen**.
- **Windows/Mac (Chrome or Edge):** open the link → click the install icon in the address bar.

Open the app once while online and wait for the green **“✓ works offline”** tag in the top bar. After that it opens with no internet at all.

## Step 5. Test offline
Turn on airplane mode, close the app, open it again from your home screen. It should work normally.

## Sharing
Send people the link. Each person opens it once online and installs it. Their results stay on their own device and never go to any server.

## Updating later
Upload a new `index.html` the same way (Add file → Upload files, same name) and change the version name in `sw.js` (for example `lablens-v1.0.1`) so phones pick up the update.

## Good to know
- If you only want a single file with no install, `index.html` alone works offline when opened from your device storage. Many phones open HTML files poorly, so the hosted link is the reliable route.
- Do not publish it as medical advice. The app already shows its disclaimers; keep them in place.
- Before wide public release, ask a licensed doctor or pharmacist to review the wording and ranges for your audience, and consider your local rules for health apps (in Nigeria, medical-device and data-protection rules such as the NDPA).
