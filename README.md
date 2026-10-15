# bitmethodgames.com

The BitMethod Games website, built with [Astro](https://astro.build) and deployed to GitHub Pages.

## Develop

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # type-checks, then builds to dist/
npm run preview  # serves dist/
```

Requires Node 22.22 or newer (see `.nvmrc`).

## Content

Page copy is markdown in `src/content/pages/`. The home page text is `src/content/pages/home.md`: its frontmatter sets the page title and meta description, and its body is the intro shown above the signup form.

New kinds of content (devlogs, game pages) go in new collections in `src/content.config.ts`.

## Signup form

The form posts to Buttondown. The newsletter username is set in `src/site.config.ts`. Signups are tagged `website`.

## Light and dark mode

The site follows the visitor's system setting. Colors are CSS variables in `src/styles/global.css`. The logo is inline SVG using `currentColor`, so it is dark on the light page and white on the dark one.

## Brand assets

Copied from `~/Code/bitmethod`, not linked:

- `src/components/Logo.astro`: `mark/bitmethod-logo-black.svg` with its fill set to `currentColor`.
- `public/favicon.svg`: `mark/bitmethod-mark-black.svg`, switching to white in dark mode.
- `public/favicon-32.png`, `public/apple-touch-icon.png`: `mark/favicon-32.png`, `mark/bitmethod-avatar-512.png`.
- `public/fonts/outfit-variable.woff2`: `font/Outfit[wght].ttf`, subset to Latin and converted to WOFF2 (SIL OFL, see `public/fonts/OFL.txt`).

Update these when the brand assets change, for example when a designer replaces the placeholder chip mark.

## Deploy

Every push to `main` builds and deploys through `.github/workflows/deploy.yml`. `public/CNAME` sets the custom domain.

One-time setup in the GitHub repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**, then set the custom domain to `bitmethodgames.com` and enable **Enforce HTTPS** once the certificate is issued.
