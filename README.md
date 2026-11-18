# White Label Portfolio — static site

A static, white-labelled portfolio website. All copy (titles, client names,
descriptions, bio, contact texts, branding) has been replaced with generic
placeholder content so the layout/design can be reused for any brand.

## Structure

```
site/                   Static export (pure static files, no build step)
  index.html            Home — work card slider
  works/<id>/           Work detail pages (Work 01 … Work 38)
  profile/ contact/     Profile and contact pages
  _payload.json         Hydration payloads (id: `<id>` per page)
  _nuxt/                Framework chunks + styles
  generate/             Pre-computed image assets (avif/webp) + fonts
  images/               Favicon / icons
server.mjs              Local preview server (binds 127.0.0.1 only)
vercel.json             Vercel static deploy config (output directory: site)
```

## Run locally

```bash
node server.mjs
# open http://127.0.0.1:8766/
```

## Deploy to Vercel

Import this repository in Vercel. `vercel.json` pins the static output
directory to `site/`, so no build command is needed — zero-config deploy.
(Alternatively, set the project's Root Directory to `site`.)

## Notes

- Every visible string is placeholder content: work titles render as
  `Work 01 … Work 38`, clients as `Client 01 … Client 38`, descriptions,
  bio and contact copy are generic dummy text. Replace them with real
  content before going live with a real brand.
- Internal CMS fetch endpoints are pointed at a dead dummy host
  (`dummy-cms.invalid`). Pages render from their pre-rendered payloads;
  client-side CMS calls fail silently.
- Fonts used: Inter + Zen Kaku Gothic New (SIL Open Font License).
- OG/share images are brand-neutral (external dummy host).
