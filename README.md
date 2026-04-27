# gradpazz-site

Official website for **Gradpazz** — campus + city resource platform.

🌐 Live: **[gradpass.site](https://gradpass.site)**
📱 App Store: **[apps.apple.com/us/app/gradpazz/id6761963554](https://apps.apple.com/us/app/gradpazz/id6761963554)**

---

## Pages

| Route | File | Purpose |
|---|---|---|
| `/` | `index.html` | Marketing home — slogan, 5 verticals, App Store CTA + QR code |
| `/support` | `support.html` | Help center — FAQ, contact, safety tips |
| `/privacy` | `privacy.html` | Privacy Policy (synced from app's i18n source) |
| `/terms` | `terms.html` | Terms of Service (synced from app's i18n source) |

Clean URLs are configured via `vercel.json` rewrites.

## Tech

Pure static HTML — no framework, no build step.

- Theme tokens mirror `apps/mobile/src/theme/index.ts` (v1.5 Refreshed Modern)
- Logo + favicon copied from `apps/mobile/assets/icon.png`
- QR code rendered live via [api.qrserver.com](https://api.qrserver.com) (no image committed)
- Hosted on **Vercel**, custom domain `gradpass.site`

## Local development

Use the Vercel CLI to preview rewrites + clean URLs locally:

```bash
npx vercel dev --listen 3737
# → http://localhost:3737
# → http://localhost:3737/support
# → http://localhost:3737/privacy
# → http://localhost:3737/terms
```

Or for plain static preview (no rewrites):

```bash
python3 -m http.server 8000
```

## Deployment

Pushes to `main` auto-deploy via Vercel.

```bash
git push origin main
```

## Brand assets

| File | Source |
|---|---|
| `logo.png` | `apps/mobile/assets/icon-transparent.png` |
| `favicon.png` | `apps/mobile/assets/icon.png` |

When the app icon changes, re-copy from the mobile app repo.

## Legal content sync

The Privacy and Terms pages are generated from the app's i18n source
(`apps/mobile/src/i18n/en.json`, keys `pp_*` and `tos_*`).
When legal content changes in the app, regenerate using the script in
git history (commit message: "build: generate legal pages from app i18n").

## License

© 2026 Gradpazz · DreamRealized Tech LLC
