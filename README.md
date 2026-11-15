# Eosyn

The Eosyn studio website, [eosyn.co.uk](https://eosyn.co.uk). Plain static HTML and CSS, with no build step.

## What's here

- `index.html`: the home page.
- `privacy/index.html`: the privacy policy (eosyn.co.uk/privacy/).
- `styles.css`: shared styles for every page.
- `brand/`: logo and app icon SVGs. Favicons and the web manifest sit at the root.
- `CNAME`: the custom domain for GitHub Pages.

## Run locally

Open `index.html` in a browser. All paths are relative, so images and icons load straight from disk.

Clicking "Privacy" from a local file shows a folder listing, not the page, because only a web server turns `privacy/` into `privacy/index.html`. Open `privacy/index.html` directly, or serve the folder:

```
npx serve .
```

## Testing

There's no code to unit test. Before merging, check every changed page in a browser in both light and dark mode, and at phone width.

## Deploying

Merging a pull request into `main` publishes the site through GitHub Pages within a minute or two. Never commit to `main` directly. See `../eosyn-context/docs/engineering.md`.
