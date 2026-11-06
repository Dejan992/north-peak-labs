# North Peak Labs

Teaser site for [North Peak Labs](https://northpeaklabs.studio/). The home page says something big is coming: software factories as a service, and the future of automated software development. The earlier consulting homepage is in git history (through `47ed5cc`) and is not published.

## Deploy

GitHub Pages serves this repository with **no build step**.

- Source: branch `main`, folder `/` (repository root)
- Custom domain: `northpeaklabs.studio`, from the `CNAME` file. HTTPS is enforced in the Pages settings.
- `.nojekyll` is present so Pages does not run Jekyll or ignore files that start with an underscore.
- Do not add a bundler or a `package.json` build unless the Pages source is changed to a GitHub Action that publishes the built files. A build that only exists locally will not run on the current host.

Pushing to `main` publishes the site. Pull requests do not.

### Local preview

From the repository root:

```bash
python3 -m http.server 8765
```

Open `http://127.0.0.1:8765/`. Fonts, the mark, and the favicon are same-origin files. The page does not call a third party.

## Production domain

The production domain is **https://northpeaklabs.studio/**. It is already set in `CNAME`, the canonical URL, Open Graph and Twitter tags, `sitemap.xml`, `robots.txt`, and the JSON-LD. Change those together if the domain ever moves.

The Google Search Console verification meta tag on the home page stays as it is.

## Contact

The public address is `hello@northpeaklabs.studio`. “Get notified” and the address on the home page are mailto links. There is no form and no calendar embed.

## What is on the site

- `index.html` — coming-soon teaser. Styles live in `styles.css`. A small script handles the theme choice.
- `self-hosting-llms-kubernetes/index.html` — decision checklist for a per-token LLM API versus self-hosting on Kubernetes. Linked from the home page footer as “Writing”.
- `404.html` — branded not-found page, `noindex`.
- `assets/` — portrait from the previous home page, kept in the repository and not linked.
- `fonts/` — self-hosted Newsreader and Inter (SIL Open Font License). License texts are in that folder.
- `mark.png`, `favicon.ico`, `favicon-32.png`, `apple-touch-icon.png` — North Peak mark.
- `og-image.png` — social preview, 1200×630.
- `robots.txt`, `sitemap.xml`, `llms.txt`.

Theme follows the operating system until the visitor chooses light or dark. The choice is stored in `localStorage` under `npl-theme`.
