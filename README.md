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
GitHub Pages serves the `main` branch root at https://vntw0n3.github.io. Push to `main` and it updates in about a minute.
