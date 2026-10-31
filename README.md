# RouteMate website

Landing page and Android downloads for RouteMate, a map-first app that lets drivers and attendants call everyone at a route stop with one tap.

- Website, at two addresses with the same content:
  - https://routemate-app.pages.dev (Cloudflare Pages, project `routemate-app`)
  - https://freddydaniel.me/routemate-site (GitHub Pages, from this repo's `main` branch; updates on every push)
- Downloads: each version's `RouteMate.apk` is attached to a [GitHub Release](../../releases). The site's download buttons always point to the latest release.

## Publishing a new version

1. Build the APK: `npx eas-cli@latest build -p android --profile preview` (in the app repo).
2. Create a release here with the APK named exactly `RouteMate.apk`:

   ```bash
   gh release create v1.0.1 RouteMate.apk --repo freddy-daniel/routemate-site --title "RouteMate 1.0.1" --notes "What changed"
   ```

## Updating the website

GitHub Pages updates by itself when you push to `main`. Cloudflare Pages doesn't: deploy the site files after pushing.

```bash
mkdir -p /tmp/routemate-site && cp index.html logo.svg /tmp/routemate-site/
npx wrangler@4 pages deploy /tmp/routemate-site --project-name routemate-app --branch main
```

Deploy only the site files (not the whole repo) so `.git` and this README stay off the site. Run `npx wrangler@4 login` first if Wrangler says you're not logged in.
