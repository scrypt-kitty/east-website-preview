# EAST — website preview

Static, **work-in-progress** mockups of the EAST (Environmental Accountability &
Strategy Team) website. Published via GitHub Pages for review only — this is not
the live site, and content/design are still in progress.

**Live (GitHub Pages):** https://scrypt-kitty.github.io/east-website-preview/

## Environments

Three environments are published from three branches (assembled by
`.github/workflows/pages.yml`), all under the one Pages site:

| Env         | Branch    | Live URL                                                              | Purpose                                             |
|-------------|-----------|----------------------------------------------------------------------|-----------------------------------------------------|
| **prod**    | `main`    | https://scrypt-kitty.github.io/east-website-preview/public/          | Approved / current site                             |
| **dev**     | `dev`     | https://scrypt-kitty.github.io/east-website-preview/dev/public/      | Integration of changes bound for prod               |
| **preview** | `preview` | https://scrypt-kitty.github.io/east-website-preview/preview/public/  | The POC currently being shown for approval          |

Root landing (`/`) and the alternate `/institute/` redesign are served from `main`.

## Workflow

- A change starts on a `feat/<date>-<slug>` branch and opens a **PR → `main`** —
  the PR's *Files changed* diff is how we compare against prod.
- Merge to **`dev`** to stage it (publishes under `/dev/`).
- Point **`preview`** at whatever POC is being shown to stakeholders
  (publishes under `/preview/`).
- On approval, merge to **`main`** (publishes prod under `/public/`).

## Notes

- Public static portions only. The members workspace and the Flask application
  live in the **private** `scrypt-kitty/east-website` repo and are **not** published here.
- Assets: `images/branding/` (EAST logos, donation QR).
- Pages is built by **GitHub Actions** (source: Actions), not "deploy from a branch."
- `.nojekyll` disables Jekyll processing so files are served as-is.
