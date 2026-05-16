# Cross Your Hart Counselling

Static website for the counselling practice. Hosted on GitHub Pages.

## Files

- `index.html` — the whole site (single page)
- `styles.css` — brand styles
- `favicon.svg` — browser tab icon
- `logo-horizontal.png` — header logo
- `logo-stacked.png` — social share image
- `.nojekyll` — tells GitHub Pages to serve files as-is

## Before going live

Open `index.html` and find-and-replace the two placeholders:

- `[your-email@example.com]` → the contact email
- `[Your area]` → e.g. "Glasgow & online across the UK"

Then commit and push to `main`.

## Publishing on GitHub Pages

1. Push this repo to GitHub.
2. In the repo on GitHub: **Settings → Pages**.
3. Under **Build and deployment**, set Source to **Deploy from a branch**, branch **`main`**, folder **`/ (root)`**, then **Save**.
4. After ~1 minute the site will be live at `https://<your-username>.github.io/crossyourhartcounselling.web/`.

## Editing copy later

All page text lives in `index.html`. Open it in any text editor and change the words between the tags — no build step required. Save, commit, push, and the live site updates within a minute.
