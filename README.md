# Wyrá website

The storefront for [Wyrá](https://wyra.pages.dev): ESP32 and Arduino devices for audio and
sensing, plus custom firmware work.

It's a plain static site, with no build step and no JavaScript: hand-written HTML and one
stylesheet. The colors come from the logo: brushed steel, copper and the amber gem on black.

## Structure

```
public/                    ← everything that gets published
├── index.html             home: hero, products, about, contact
├── audio-hub/             Wyrá Audio Hub product page
├── gift-box/              Magic Gift Box product page
├── server-room-monitor/   case study
├── services/              custom work
├── 404.html
├── assets/css/site.css    all styles (palette tokens at the top)
├── assets/img/            logo, icons, share image, device screenshots
├── _headers               security and cache headers (Cloudflare Pages)
├── robots.txt
└── sitemap.xml
```

## Run it locally

```bash
python -m http.server 8766 --directory public
```

Then open <http://localhost:8766>.

## Deploy

Hosted on Cloudflare Pages, connected to this repository:

- **Framework preset:** None
- **Build command:** *(empty)*
- **Build output directory:** `public`

Every push to `main` publishes the site.

## When the domain changes

The site starts on `wyra.pages.dev`. After adding a custom domain, replace
`https://wyra.pages.dev` in the `<link rel="canonical">` and `og:` tags of each page, in
`robots.txt` and in `sitemap.xml`.

## Notes

- The Content-Security-Policy in `_headers` allows no scripts. If you turn on Cloudflare Web
  Analytics or embed a video, add their domains to the policy.
- `assets/img/` images are generated from the logo and from the Audio Hub firmware's web pages.

© 2026 Wyrá · Sergio Levy. All rights reserved.
