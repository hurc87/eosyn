# Eosyn website — context for Claude

@../eosyn-context/CLAUDE.md
@../eosyn-context/docs/engineering.md
@../eosyn-context/docs/brand.md
@../eosyn-context/docs/company.md

## This project

- What it is: the Eosyn studio website, eosyn.co.uk. Plain static HTML and CSS, with no build step and no framework.
- Hosting: GitHub Pages, published from `main` (custom domain set in `CNAME`). Merging a pull request into `main` puts it live within a minute or two.
- Pages: `index.html` (home) and `privacy/index.html` (privacy policy). Both use the shared `styles.css`.

## Project-specific notes

- **Use relative paths only** (`brand/...`, or `../brand/...` from a subfolder), never paths starting with `/`. Root-relative paths break when the files are opened straight from disk.
- **Logo and icon files** in `brand/` and the root are copies from `../eosyn-context/assets/brand/`. Update them there first, then copy them here. Never redraw a logo.
- **The privacy policy describes what the site and Pharos actually do.** If the site adds a third-party service (analytics, embeds, forms, fonts), or Pharos starts collecting or sending any data, update `privacy/index.html` and its "last updated" date in the same pull request.
- The site sets no cookies and has no analytics. Keep it that way unless the founders decide otherwise. If they do, record it in `../eosyn-context/docs/decisions.md`.
