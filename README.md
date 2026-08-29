# Nurture Early Learning — website

The website for [Nurture Early Learning](https://nurture-earlylearning.com.au), a boutique
early childhood care and education service in Biloela, Queensland.

## How it works

- Plain static HTML ([index.html](index.html)) and hand-written CSS
  ([styles/styles.css](styles/styles.css)) — no build step, no frameworks.
- Fonts (Playfair Display, Quicksand) load from Google Fonts; everything else is local.
- Photos live in [assets/images/](assets/images/) — see the README there for the expected
  filenames.

## Deployment

Hosted on GitHub Pages with the custom domain `nurture-earlylearning.com.au`
(DNS managed at GoDaddy, pointed at GitHub Pages).

Every push to `main` runs [.github/workflows/static.yml](.github/workflows/static.yml):

1. **Checks** — HTML validation (`html-validate`) and internal link/image checking
   (`lychee`). Pull requests run these checks without deploying.
2. **Deploy** — publishes the repository to GitHub Pages, only if the checks pass.

To publish a change: edit, commit, push to `main`. That's it.
