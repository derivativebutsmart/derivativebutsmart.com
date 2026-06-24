# derivativebutsmart.com

Static marketing site for Derivative But Smart LLC and its apps.

## Structure

- `index.html` — company home
- `pdfvault/` — PDFVault product page
- `pdfvault/privacypolicy/`, `pdfvault/tos/` — PDFVault legal pages
- `styles.css`, `logoV1.png` — shared assets

All asset and link paths are **root-absolute** (`/styles.css`, `/pdfvault`),
so they resolve identically regardless of page depth. This means the site
must be served from a domain root — which is how both target hosts work.

## Local development

Don't open the `.html` files directly (`file://` won't serve `index.html`
for a directory, and absolute `/` paths won't resolve). Run a static server
from the repo root so it behaves like production:

```sh
python3 -m http.server 8000
```

Then visit http://localhost:8000 and click through normally.

## Deployment

- **GitHub Pages**: enable Pages for the repo. The `CNAME` file points the
  custom domain `derivativebutsmart.com` at it; add the matching DNS records
  at the registrar (Porkbun).
- **Porkbun static hosting**: upload the repo contents to the site root.

Either way the site is served from `/`, so the absolute paths just work.
