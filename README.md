# Cross Your Hart Counselling

Static website for the counselling practice. Built as plain HTML, CSS, and
a little vanilla JavaScript with no build step. Hosted on GitHub Pages and
served at **https://crossyourhartcounselling.co.uk**.

For contributor conventions (voice, accessibility rules, image tooling),
see `CLAUDE.md`.

## Files

- `index.html`: the whole site (a single page of anchor-linked sections)
- `styles.css`: all styling; design tokens live in the `:root` block
- `favicon.svg`: browser tab icon
- `logo-horizontal.png`: header logo
- `og-image.jpg`: 1200x630 image shown when the site is shared on social media
- `bacp-logo.png`: BACP registered-member badge (footer)
- `hannah.jpg`: portrait used in the hero
- `CNAME`: the custom domain, used by GitHub Pages
- `.nojekyll`: tells GitHub Pages to serve files as-is

## Editing the site

All page text lives in `index.html`. Open it in any text editor, change
the words between the tags, then save, commit, and push to `main`. No
build step is required and the live site updates within about a minute.

To preview locally before pushing:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Hosting

The site is published from the `main` branch (root folder) under
**Settings -> Pages**, with the custom domain `crossyourhartcounselling.co.uk`
(set by the `CNAME` file) and HTTPS enforced. Any push to `main` redeploys
automatically.
