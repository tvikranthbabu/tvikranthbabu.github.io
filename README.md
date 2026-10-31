# vikranthbabu.co.uk

Personal site of Vikranth Babu T (https://vikranthbabu.co.uk; repo `tvikranthbabu/tvikranthbabu.github.io`), built with [Quarto](https://quarto.org). GitHub builds and publishes it automatically on every push to `main` (see `.github/workflows/publish.yml`).

## Where things are

| Path | What it is |
|---|---|
| `index.qmd` | Home and About page |
| `work.qmd` | Projects and Case Studies page (project cards with filters) |
| `_drafts/` | Write-ups in progress: kept on this machine only (git-ignored), never published |
| `projects.qmd` | Personal projects, hidden for now (`draft: true`) |
| `_quarto.yml` | Site name, top navigation, footer |
| `styles.scss` | Colours, fonts and all the page components. Change `$accent` to re-colour the site |
| `assets/images/` | Photo and favicon |
| `assets/files/Vikranth-Babu-T-CV.pdf` | The public CV (no phone number). Every CV button links here: to update it, replace this file and keep exactly this name |

## What goes on the site

**The rule: if a sentence would be fine on LinkedIn, it can go on the site.** Public pages say what the problem was, what I owned, the judgement call and the claimable result, then invite a conversation. Internal segmentations, system and pipeline design, model and vendor choices, internal experiment results and example outputs stay out. Full deep dives live in private decks shared on request. The repo is public too, so detailed drafts never get committed here.

## Editing

Pages are Markdown (`.qmd`). The home page and the Projects page use HTML blocks for the cards; copy an existing `<article class="pc">` block to add another (the `data-` attributes drive the filters).

To preview on your own machine (optional): install Quarto from quarto.org, then run `quarto preview` in this folder.

## Showing the Projects page

Remove `draft: true` from `projects.qmd` and uncomment the Projects link in `_quarto.yml`.

## Publishing

1. Settings → Pages → Build and deployment → Source: **GitHub Actions** (one time).
2. Push to `main`. The "Publish site" workflow renders and deploys; the Actions tab shows progress.
3. **Site address:** `https://vikranthbabu.co.uk` (the old `https://tvikranthbabu.github.io` address redirects there). Links are relative; `site-url` in `_quarto.yml` sets the absolute address used for link previews.

## Custom domain

`vikranthbabu.co.uk` (bought 31 Oct 2026 at names.co.uk, with `vikranthbabu.com`, which forwards to it). Set up:

1. GitHub → profile Settings → Pages → **Add a verified domain** → add the TXT record GitHub shows at the registrar, then Verify (stops anyone else claiming the domain).
2. Repo Settings → Pages → Custom domain: `vikranthbabu.co.uk` → Save. No `CNAME` file is needed: with a GitHub Actions workflow, GitHub ignores it.
3. DNS at names.co.uk (delete any default/parking records for `@`, `www` and `*` first):
   - `@` A → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `@` AAAA → `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - `www` CNAME → `tvikranthbabu.github.io`
4. When the Pages check turns green and the certificate is issued, tick **Enforce HTTPS**.
5. `vikranthbabu.com`: web forwarding (301, permanent) at names.co.uk → `https://vikranthbabu.co.uk`.
