# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added
- Privacy policy page at `/privacy/`, covering the website, emails to support and the Pharos app.
- "Privacy" link in the footer of every page.
- Pharos terms of use page at `/pharos/terms/`, linked from the footer of every page.
- Project docs: `CLAUDE.md`, this changelog and `docs/build-journal.md`.

### Changed
- Page styles moved out of `index.html` into a shared `styles.css`.
- README updated: the site can be opened straight from disk.

### Fixed
- Registered office address now includes Ross Way.

## [0.1.0] - 2026-11-13

First version, live at eosyn.co.uk.

### Added
- Single-page studio website: introduction, Pharos preview and contact email.
- Eosyn logo (light and dark versions), favicons and web app manifest.
- Light and dark mode, following the device setting.
- Footer with company number and registered office.
- Custom domain (`CNAME`) for GitHub Pages.

### Fixed
- Images and icons failing to load when the page was opened straight from disk (root-relative paths changed to relative).
- Eosyn logo cut off on the right (SVG viewBox widened from 763 to 833).
