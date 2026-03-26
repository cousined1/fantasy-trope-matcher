# Fantasy Trope Matcher 🗡️✨

**"Which Story Was Written For You?"**

A viral personality quiz app that matches BookTok/fantasy romance readers to their signature tropes — and routes them directly to Edward's KDP book series.

## Live Demo
Deploy to: [GitHub Pages] or [Netlify] (single HTML file, zero dependencies)

## What It Does

1. **8-question personality quiz** — answers reveal subconscious trope preferences
2. **Email gate** — captures leads before revealing full result (skip option respects UX)
3. **10 possible results** — each maps to one of the 3 KDP series:
   - Enemies-to-Lovers / Dark Protector / Battle-Forged Magic → **Imani: The Warrior Nun**
   - Chosen One / Slow Burn / Forbidden Bond → **Amara: The Enchantress**
   - Warrior Queen / Fated Mates / Rivals-to-Lovers / Redemption Arc → **Wendy: The Chosen Empress**
4. **Direct Amazon CTA** on results page
5. **Social sharing** — TikTok (clipboard + open), Twitter intent URL, Copy link

## Why It Works

- `#fantasyromance` has **93M+ posts** on TikTok
- "What trope are you?" is an inherently shareable identity statement
- Friend challenge mechanic ("compare your tropes") creates viral loop
- Email capture creates ongoing KDP marketing list
- Zero friction — one HTML file, no backend required (email can wire to n8n webhook later)

## Deploy

```bash
# GitHub Pages — just push index.html to a gh-pages branch
# Netlify Drop — drag index.html to netlify.com/drop
# Coolify — serve as static site
```

## Wire Email Capture to n8n

In `index.html`, find the `submitEmail()` function and add:
```js
// POST to n8n webhook
fetch('http://10.0.0.237:30109/webhook/trope-matcher-email', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email, topTropes, result: primary, timestamp: new Date().toISOString() })
});
```

## SEO Tags
All meta tags included for Twitter Card + OpenGraph sharing.

---
*Built during nightly build session — March 24, 2026*
