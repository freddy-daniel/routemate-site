# RouteMate website

Landing page and Android downloads for RouteMate, a map-first app that lets drivers and attendants call everyone at a route stop with one tap.

- Website: served by GitHub Pages from this repo's `main` branch.
- Downloads: each version's `RouteMate.apk` is attached to a [GitHub Release](../../releases). The site's download buttons always point to the latest release.

## Publishing a new version

1. Build the APK: `npx eas-cli@latest build -p android --profile preview` (in the app repo).
2. Create a release here with the APK named exactly `RouteMate.apk`:

   ```bash
   gh release create v1.0.1 RouteMate.apk --repo freddy-daniel/routemate-site --title "RouteMate 1.0.1" --notes "What changed"
   ```
