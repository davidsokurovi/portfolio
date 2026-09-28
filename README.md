# David Sokurovi — Portfolio

My personal portfolio site: a short bio, education, core skills, and a set of data
analytics projects (mostly Tableau dashboards, plus my Penske internship work and
undergraduate thesis).

**Live site:** https://davidsokurovi.github.io/portfolio/

## Built with

- Plain HTML5, CSS3, and jQuery — no build step, no framework, no bundler
- [Tableau Public](https://public.tableau.com/app/profile/david.sokurov/vizzes) for the dashboards themselves
- [Magnific Popup](https://dimsemenov.com/plugins/magnific-popup/) for the project detail popups
- [FlexSlider](https://woocommerce.com/flexslider/) for the testimonials slider
- Based on the free **Ceevee** template by [StyleShout](https://www.styleshout.com/), heavily customized since

## Project structure

```
index.html                  All page content and structure (single page)
css/
  default.css                Base template styles
  layout.css                 Page-specific layout and every custom section
                              (hero, project list, popups, etc.)
  media-queries.css          Responsive breakpoints
  magnific-popup.css         Popup plugin styles
  fonts.css, fontello/,      Web fonts and icon fonts
  font-awesome/
js/
  init.js                     All page behavior (smooth scroll, popups, nav,
                               slider) — one file, no build step
  jquery-*.js, modernizr.js,  Third-party libraries the template ships with
  magnific-popup.js, etc.
images/
  header-background.jpg      Hero background image
  link-preview.jpg           Social/link preview image (Open Graph / Twitter card)
  portfolio/
    modals/                  Full-size screenshots shown in each project popup
    thumbs/                  Small (640px) copies shown in the project list
```

## Running locally

No install or build step — it's static HTML. Either:

- Open `index.html` directly in a browser, or
- Serve it locally so relative paths behave exactly like production:
  ```
  python3 -m http.server 8000
  ```
  then visit `http://localhost:8000`.

## Deployment

The site is served by **GitHub Pages** from the `main` branch of this repo, at
https://davidsokurovi.github.io/portfolio/. Pushing to `main` redeploys it —
GitHub usually takes a minute or two to rebuild, and browsers can cache the old
CSS/JS for up to ~10 minutes afterward.

To force a browser to pick up a CSS/JS change immediately, bump the version
query string on its `<link>`/`<script>` tag in `index.html` (e.g.
`css/layout.css?v=29` → `?v=30`) — that's why those numbers keep climbing.
