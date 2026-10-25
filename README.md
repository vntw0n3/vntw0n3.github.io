# antonio: freelance site (repo: vntw0n3)

Single-page static site: plain HTML, CSS and JS. No build step. Kept separate from the job portfolio (`antoniograyportfolio`) on purpose: different brand, no cross-links, no employer details.

## Editing
- **Content:** `index.html`, one commented block per section (Services, Work, Process, Contact).
- **Colors:** tokens at the top of `styles.css` (`--accent` is the mint accent).
- **Project images:** `img/<name>-480|800.webp|jpg`, 16:10. Replace both sizes when a project changes.

## Preview locally
```bash
python -m http.server 4328
```

## Deploy
Live at https://freelance.grayareaart.com, served by the Cloudflare Pages project `freelance-grayareaart` (direct upload, no build). Contact mail to `freelance@grayareaart.com` is caught by the `mail-forwarder` Worker. DNS for grayareaart.com is at Wix: `freelance` is a CNAME to `freelance-grayareaart.pages.dev`.

```bash
rm -rf .deploy && mkdir .deploy && cp -r index.html styles.css script.js favicon.svg .deploy/ && mkdir .deploy/img && find img -maxdepth 1 -type f -exec cp {} .deploy/img/ \;
CLOUDFLARE_API_TOKEN=... CLOUDFLARE_ACCOUNT_ID=... npx wrangler pages deploy .deploy --project-name freelance-grayareaart --branch main
```

The old https://vntw0n3.github.io redirects here from the `gh-pages` branch.
