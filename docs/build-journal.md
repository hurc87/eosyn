# Build journal — Eosyn website

A plain-English story of how this website was built, written as raw material for a future blog post or YouTube tutorial.

---

### 2026-11-13 — Going live, and why the logo vanished

**Goal:** get a simple one-page website live at eosyn.co.uk, so the Apple Developer organisation enrolment (which needs a company website) can go ahead.

**Tech used and why:**

- **Plain HTML and CSS, no framework.** One page with some text, a logo and an email link doesn't need React or a build step. With nothing to compile, there's nothing to break, and anyone can open the file and read it.
- **GitHub Pages for hosting.** It's free, includes HTTPS, and publishes automatically whenever a change is merged into `main`. That fits our rule that `main` is always the live, working version.
- **IONOS keeps the domain and email.** A `CNAME` file in the repo tells GitHub Pages which domain to answer to. A matching DNS record at IONOS points the domain at GitHub.
- **Light and dark mode with `prefers-color-scheme`.** The page follows the phone or computer's own setting. The logo swaps between its light and dark versions with a `<picture>` element, so the wordmark is always readable.

**Problems and fixes:**

- **Logos missing when the file was opened directly.** Every image path started with a slash (`/brand/logo.svg`). A leading slash means "start from the root of the site." On a web server that's the site folder. When you double-click the file, it's the root of your C: drive, where there's no `brand` folder. Removing the slash (`brand/logo.svg`) makes the path relative to the page, which works both ways.
- **Logo cut off on the right.** An SVG's `viewBox` is the window you see the drawing through. The wordmark was wider than the window (763 units), so the end of the "N" was clipped. Widening it to 833 fixed it. The same fix went into the master files in the context repo.

**Screenshot / recording moments:** the page with broken images next to the fixed one; the SVG opened in a text editor with the `viewBox` highlighted.

**Next:** a privacy policy, which both app stores need before Pharos can be published.

---

### 2026-11-15 — Privacy policy

**Goal:** a privacy policy at eosyn.co.uk/privacy/. The App Store and Google Play both ask for a privacy policy link before an app can be published, and the website needs one anyway.

**Tech used and why:**

- **A folder with its own `index.html`** (`privacy/index.html`). Web servers serve `index.html` when you visit a folder, so the address is a tidy `/privacy/` and not `/privacy.html`.
- **A shared stylesheet.** The homepage's CSS lived inside `index.html`. With a second page, copying it would mean two versions that slowly drift apart, so it moved into `styles.css` and both pages link to it.

**Key steps:**

1. Read the app's code before writing anything, so the policy describes what Pharos really does, not what we think it does.
2. Wrote the policy in plain English, with a "short version" at the top for people who won't read the rest.
3. Added a Privacy link to every page's footer.

**Problems and how they were solved:**

- **"No third parties" wasn't quite true.** The site loads its font (Montserrat) from Google Fonts, so every visitor's browser contacts Google, and Google sees their IP address. The options were to host the font ourselves or to say so in the policy. We chose to say so for now. Hosting the font ourselves stays open for later.
- **The camera does more than we'd said.** The brief said the camera is only used to read Morse code. In fact, on phones the torch belongs to the camera, so Pharos needs camera permission just to switch the light on. The policy explains both uses.
- **Apple and Google can share stats.** Even an app that collects nothing can receive anonymous crash reports and download numbers from Apple and Google, if the user has opted in on their phone. The policy says so, to be fully honest.

**Screenshot / recording moments:** the policy page in light and dark mode; the app's `app.json` showing the camera as the only permission.

**Next:** if Pharos ever adds analytics, ads, purchases or anything that sends data off the phone, the policy must be updated before that release.
