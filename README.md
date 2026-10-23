# Election Research & Analytics

GitHub Pages portfolio for three existing election research websites. The supplied HTML applications are kept as standalone pages and grouped into folders.

## Project structure

```text
.
├── index.html
├── prnn9/
│   └── index.html
├── warroom/
│   ├── prnjohor2026.html
│   └── keputusanprnjohor2026.html
├── .nojekyll
└── .github/workflows/pages.yml
```

## Pages included

| Path | Page |
| --- | --- |
| `/prnn9/` | PRN Negeri Sembilan 2026 dashboard and simulator |
| `/warroom/prnjohor2026.html` | PRN Johor 2026 post-mortem report |
| `/warroom/keputusanprnjohor2026.html` | PRN Johor 2026 Election Intelligence Hub |

The two Johor pages link to each other using relative paths, so they continue to work on GitHub Pages and under a project-site base path.

## Important runtime note

The Negeri Sembilan page calls `api/ai-assistant.php` for its server-side AI assistant. That PHP endpoint was not included among the supplied files, and GitHub Pages does not run PHP. The rest of the static dashboard and local simulator can be hosted there, but the AI assistant needs a separate backend service. Do not put a private API key in frontend JavaScript or commit it to this repository.

The HTML pages load libraries such as Chart.js, Leaflet, ECharts, and web fonts from public CDNs. Those parts need an internet connection in the visitor's browser.

## Publish as `zaipul.github.io`

A GitHub profile page at `https://zaipul.github.io/` uses a repository named exactly `zaipul.github.io`.

1. Create a new public repository named `zaipul.github.io` under the `zaipul` account, or use an existing Pages repository if you already have one.
2. Upload the contents of this folder to the repository root. Keep the `.github/workflows/pages.yml` workflow and `.nojekyll` file.
3. In **Settings → Pages**, set the build and deployment source to **GitHub Actions**.
4. Commit to the `main` branch. The workflow deploys the site; follow its run under the repository's **Actions** tab.
5. Once deployment succeeds, open `https://zaipul.github.io/`.

If these files are placed in a repository named something else, GitHub Pages uses a project URL such as `https://zaipul.github.io/REPOSITORY-NAME/`.

## Run locally

From this folder, run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. A local server is recommended because the pages use fetch and browser APIs.

## Source files

The three application pages were prepared from the HTML files supplied for this task. Their layout and application logic are retained; the two Johor cross-links are changed to relative links for this package. No PHP backend or API credentials are included.
