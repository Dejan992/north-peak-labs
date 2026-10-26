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

Open `http://127.0.0.1:8765/`. Fonts, the mark, and the favicon are same-origin files. The page does not call a third party.

## Production domain

The production domain is **https://northpeaklabs.studio/**. It is already set in `CNAME`, the canonical URL, Open Graph and Twitter tags, `sitemap.xml`, `robots.txt`, and the JSON-LD. Change those together if the domain ever moves. No domain placeholder is required.

## TODO before the contact path is real

Search the repo for `TODO`. These are the ones that matter:

1. **Contact email.** Replace `TODO_CONTACT_EMAIL@northpeaklabs.studio` everywhere it appears (`index.html`, including the `data-contact-email` attribute and the no-JavaScript mailto, plus `llms.txt`). Then add an `"email"` field on the Organization node in the JSON-LD.
2. **Booking link.** Set `data-booking-url` on `<body>` in `index.html` to an `https://` calendar URL. Leave it empty until that link exists. The “Book an advisory call” button stays on the contact section until then.
3. **Portrait.** Replace the `DR` monogram in the about section with a real photo. Use `width`, `height`, `alt` that describes the photo, and `loading="lazy"`. A commented example is next to the monogram.
4. **Selected work.** Replace the work-section placeholder with engagements a client has agreed to describe. Situation, work, outcome. No invented metrics.
5. **Rates (optional).** A placeholder under Engagements is where call length, fees, or retainer cadence can go. Remove that note if they should stay off the site.

The earlier product page used `dan.rajkovic@icloud.com`. The previous README listed `drajkovic@mail.grokbot.com`. Neither is assumed to be the public consulting inbox. Pick the address on purpose.

Do not add client logos, testimonials, headcount, certifications, or case studies that are not real. Do not name employers on this site.

## What is on the page

- `index.html` — the whole site: copy, CSS, and a small script (theme, menu, scroll reveal, mailto form).
- `404.html` — branded not-found page, `noindex`.
- `fonts/` — self-hosted Newsreader and Inter (SIL Open Font License). License texts are in that folder.
- `mark.png`, `favicon.ico`, `favicon-32.png`, `apple-touch-icon.png` — existing North Peak mark.
- `og-image.png` — social preview, 1200×630.
- `robots.txt`, `sitemap.xml`, `llms.txt`.

Theme follows the operating system until the visitor chooses light or dark. The choice is stored in `localStorage` under `npl-theme`.

## Lighthouse

Scores are recorded in the pull request after a local mobile audit. Re-run from this folder with Chrome installed:

```bash
npx --yes lighthouse http://127.0.0.1:8765/ --only-categories=performance,accessibility,best-practices,seo --form-factor=mobile --screenEmulation.mobile=true --output=json --output-path=/tmp/lh.json --chrome-flags="--headless --no-sandbox"
```
