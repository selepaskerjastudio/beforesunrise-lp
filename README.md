# Before Sunrise* — Landing

Static landing page for **Before Sunrise\***, a daily-amalan habit tracker PWA.

Imported from the Claude Design project *Before Sunrise\* App* — variant **1b "Fajar"**
(`Before Sunrise Landing.dc.html`). The design-canvas runtime (`x-dc`, `sc-if`,
`support.js`) is stripped; all conditional blocks (`heroPhone`, `showTestimoni`,
`showFaq`) are rendered unconditionally.

## Files

- `index.html` — the whole page. No build step, no JS, one external request (Google Fonts).
- `.nojekyll` — tells GitHub Pages to serve files as-is.

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

- Add an OG image (`og:image`) — none in the design yet.
- Set `og:url` / canonical once the final landing domain is decided.
