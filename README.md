# tvikranthbabu.github.io

Personal site of Vikranth Babu T (https://tvikranthbabu.github.io), built with [Quarto](https://quarto.org). GitHub builds and publishes it automatically on every push to `main` (see `.github/workflows/publish.yml`).

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
3. **Site address:** `https://tvikranthbabu.github.io`. Links are relative, so a custom domain works without changes.

## Custom domain

1. Buy the domain (Cloudflare Registrar or Namecheap; check the renewal price).
2. Settings → Pages → Custom domain: enter it, then add a file named `CNAME` (containing the domain) to the repo root and list it under `resources` in `_quarto.yml`.
3. DNS: `www` → CNAME → `tvikranthbabu.github.io`; apex → A records `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
4. Tick "Enforce HTTPS".
