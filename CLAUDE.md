# Cross Your Hart Counselling — project guide

Single-page static brochure site for a BACP-registered counsellor. Plain
HTML + CSS + a little vanilla JS. **No build step, no dependencies, no
framework.** Edit the files and push.

## Layout

- `index.html` — the entire site (one page, anchor-linked sections)
- `styles.css` — all styling; design tokens live in `:root` (colours,
  fonts, spacing, shadows)
- JS is a small inline `<script>` at the bottom of `index.html`
  (mobile nav toggle, reveal-on-scroll, current-year stamp)

## Run it locally

No tooling required:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

GitHub Pages, `main` branch, `/` (root). **Pushing to `main` publishes
within ~1 minute.** Custom domain `crossyourhartcounselling.co.uk` is set
via the `CNAME` file; `.nojekyll` makes Pages serve files as-is.

## Voice & copy conventions

Match the existing tone — it is deliberate:

- Calm, plain, human; never clinical or salesy. Person-centred framing
  ("I'm not here to fix you", "you're not broken").
- **UK spelling** (counsellor, person-centred, recognise).
- **No em dashes** — they read as AI-written. Use commas, colons, or full
  stops instead. (See git history.)
- All copy lives in `index.html`; no CMS.

## Things to preserve when editing

A deliberate accessibility/performance pass was done — don't regress it:

- **Contrast:** `--text-mute` is tuned to just pass WCAG AA (4.5:1) on the
  cream backgrounds. Don't lighten it.
- **Focus:** every interactive element has a visible `:focus-visible`
  ring. Don't add `outline: none` without a replacement.
- **Images:** always set explicit `width`/`height` on `<img>` to prevent
  layout shift, and resize source images to roughly the size they render
  at (the portrait and logos are downscaled, not full-res).
- **Motion:** reveal animations respect `prefers-reduced-motion`; keep any
  new animation behind that guard.

## Image tooling

Only macOS `sips` is available locally (no `cwebp`/`magick`/`pngquant`),
so assets are optimised JPEG/PNG rather than WebP/AVIF. To resize:

```sh
sips --resampleWidth 700 -s format jpeg -s formatOptions 72 in.jpg --out out.jpg
```

## Assets

- `hannah.jpg` — hero portrait (≈700×880), also fine for general use
- `logo-horizontal.png` — header logo (≈600×169)
- `og-image.jpg` — 1200×630 social-share card (the landscape logo centred
  on the brand background `#faf5f0`). Regenerate if the logo changes;
  referenced by **absolute** URL in the `og:`/`twitter:` meta tags, so it
  only resolves once the custom domain is live.
- `bacp-logo.png` — Hannah's **personalised** BACP member badge
  (Registered Member 401693). This is a collective mark: it must be
  Hannah's own logo downloaded from her BACP account, used **unaltered**
  (no recolouring/cropping) per BACP policy. Never substitute another
  member's badge.
- `favicon.svg`
- `logo-stacked.png` — currently unused (the README's note calling it the
  social image is stale; the share image is now `og-image.jpg`).

## Commit style

Match the existing log: imperative subject ≤50 chars, no trailing period,
and a body that explains *why* (not what). e.g. "Shrink oversized images
and reserve their space".
