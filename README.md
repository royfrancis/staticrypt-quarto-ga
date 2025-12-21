# staticrypt-quarto-ga [![action](https://github.com/royfrancis/staticrypt-quarto-ga/workflows/staticrypt/badge.svg)](https://github.com/royfrancis/staticrypt-quarto-ga/actions?workflow=staticrypt)

Password locking quarto website using StatiCrypt and Github actions.

## How it works

1. **Render with Quarto** – The GitHub Actions workflow installs Quarto and runs `quarto render`, placing the generated site in `docs/` (as configured in `_quarto.yml`).
2. **Lock HTML with StatiCrypt** – Every HTML file inside `docs/` is re-encrypted in place using the StatiCrypt Docker image. The password is supplied via the `STATICRYPT_PASSWORD` secret, so make sure that secret is defined in the repository settings.
3. **Deploy to Pages** – Once all files are locked, the workflow uploads the `docs/` artifact and deploys it to GitHub Pages using the standard `configure-pages`, `upload-pages-artifact`, and `deploy-pages` steps.

Refer to `.github/workflows/staticrypt.yml` if you need to tweak build targets, add extra content processing, or change deployment behavior.

---

2026 • Roy Francis
