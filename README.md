# North Peak Labs

Consulting site for [North Peak Labs](https://northpeaklabs.studio/), the one-person Arizona practice of Dejan Rajkovic. The page covers AI platform and MLOps advisory, LLM system architecture, cloud and Kubernetes, AI strategy, and expert-network calls.

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

Open `http://127.0.0.1:8765/`. Fonts, the mark, the portrait, and the favicon are same-origin files. The page does not call a third party.

## Production domain

The production domain is **https://northpeaklabs.studio/**. It is already set in `CNAME`, the canonical URL, Open Graph and Twitter tags, `sitemap.xml`, `robots.txt`, and the JSON-LD. Change those together if the domain ever moves.

## Contact and booking

The public address is `rajkovic@mail.grokbot.com` (`data-contact-email` on `<body>`, the mailto links, and the Organization email in the JSON-LD).

“Book an advisory call” opens a mailto to that address with the subject `Advisory call request`. If `data-booking-url` is set to an `https://` calendar link, that button uses the calendar instead.

## Portrait

`assets/dejan-rajkovic.webp` is served first, with `assets/dejan-rajkovic.jpg` as the fallback. The image is 400×400 and is displayed at 400px or smaller.

## Background

The background section is in-house engineering, not client work. Employers are not named.

## What is on the page

- `index.html` — the whole site: copy, CSS, and a small script (theme, menu, scroll reveal, mailto form).
- `404.html` — branded not-found page, `noindex`.
- `assets/` — portrait, JPEG and WebP.
- `fonts/` — self-hosted Newsreader and Inter (SIL Open Font License). License texts are in that folder.
- `mark.png`, `favicon.ico`, `favicon-32.png`, `apple-touch-icon.png` — existing North Peak mark.
- `og-image.png` — social preview, 1200×630.
- `robots.txt`, `sitemap.xml`, `llms.txt`.

Theme follows the operating system until the visitor chooses light or dark. The choice is stored in `localStorage` under `npl-theme`.
