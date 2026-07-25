# Before Sunrise* — Landing

Static landing page for **Before Sunrise\***, a daily-amalan habit tracker PWA.

Imported from the Claude Design project *Before Sunrise\* App* — variant **1b "Fajar"**
(`Before Sunrise Landing.dc.html`). The design-canvas runtime (`x-dc`, `sc-if`,
`support.js`) is stripped; all conditional blocks (`heroPhone`, `showTestimoni`,
`showFaq`) are rendered unconditionally.

## Files

- `index.html` — the whole page. No build step, no JS, one external request (Google Fonts).
- `og-image.html` — source for the social card (1200×630 layout, app mockup on the right).
- `og.jpg` — rendered social card, 2400×1260, referenced by `og:image` / `twitter:image`.
- `.nojekyll` — tells GitHub Pages to serve files as-is.

### Regenerating og.jpg

Edit `og-image.html`, then:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu \
  --hide-scrollbars --window-size=1200,630 --force-device-scale-factor=2 \
  --virtual-time-budget=10000 --screenshot=og.png "file://$PWD/og-image.html"
sips -s format jpeg -s formatOptions 82 og.png --out og.jpg && rm og.png
```

## Deploy

Hosted on GitHub Pages from `selepaskerjastudio/beforesunrise-lp`, branch `main`,
folder `/` (root). Any push to `main` republishes.

```bash
git push origin main
```

Live at <https://selepaskerjastudio.github.io/beforesunrise-lp/>.

For a custom domain (`beforesunrise.id`), add a `CNAME` file containing the
domain and point DNS at GitHub Pages.

All CTAs link to the app at <https://app.beforesunrise.id>.

## Design notes

- Type: Hanken Grotesk 400–900.
- Palette: sand `#F6F1EA`, cream `#FFFBF7`, ink `#17120E`, flame `#F0451F`, gold `#FFC56B`.
- Hero gradient: `linear-gradient(170deg,#2A2350,#7A3B5E 42%,#E66A3C 78%,#FFB257)`.
- The phone mockup is a 402×858 CSS screen scaled via `--phone-scale`
  (0.62 → 0.78 across breakpoints) and cropped so it peeks out of the hero.
- Breakpoints: 420px (phone scale), 560px (2-col features, row CTAs),
  900px (two-column hero, 3-col features/quotes, 2-col FAQ).

## TODO

- If the landing moves to a custom domain, update `og:url`, `og:image`,
  `twitter:image`, and `<link rel="canonical">` in `index.html` — Open Graph
  requires absolute URLs.
