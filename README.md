# Nurture Early Learning — website

The website for [Nurture Early Learning](https://nurture-earlylearning.com.au), a boutique
early childhood care and education service in Biloela, Queensland.

## How it works

- Plain static HTML ([index.html](index.html)) and hand-written CSS
  ([styles/styles.css](styles/styles.css)) — no build step, no frameworks.
- Fonts (Playfair Display, Quicksand) load from Google Fonts; everything else is local.
- Photos live in [assets/images/](assets/images/) — see the README there for the expected
  filenames.

## How to add a page

Pages live in their own folder so URLs stay clean (`philosophy/index.html` →
`/philosophy/`). To add one:

1. Copy an existing subpage, e.g. `philosophy/index.html`, into a new folder:
   `educators/index.html`.
2. Update its `<title>`, `<meta name="description">`, the `.page-hero` heading, and the
   body content. Move the `class="active"` / `aria-current="page"` markers in the nav to
   the new page's own link.
3. Add the new link to the nav `<ul>` **and** the footer quick links on *every* page
   (the header/footer are duplicated per page — there is no build step, so a nav change
   means touching each HTML file).
4. Always use root-absolute paths for shared assets and cross-page links
   (`/styles/styles.css`, `/assets/images/...`, `/philosophy/`, `/#contact`).
5. Push — CI validates every page and checks all internal links before deploying.

## Deployment

Hosted on GitHub Pages with the custom domain `nurture-earlylearning.com.au`
(DNS managed at GoDaddy, pointed at GitHub Pages).

Every push to `main` runs [.github/workflows/static.yml](.github/workflows/static.yml):

1. **Checks** — HTML validation (`html-validate`) and internal link/image checking
   (`lychee`). Pull requests run these checks without deploying.
2. **Deploy** — publishes the repository to GitHub Pages, only if the checks pass.

To publish a change: edit, commit, push to `main`. That's it.
