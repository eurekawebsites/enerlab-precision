# Enerlab Precision — Company Website

Static landing page for Enerlab Precision. Separate from, and unrelated to,
the **Enerlab Informes** application (a different Firebase-hosted product).
Nothing here touches that project's code, Firebase config, or deployment.

## Structure

```
enerlab-precision/
├── index.html              # The entire site (currently: logo hero + footer)
├── assets/
│   ├── css/
│   │   └── styles.css      # All styling; brand colors sampled from the logo file itself
│   └── img/
│       ├── enerlab-precision-logo.png   # Full logo, optimized (source: enerlab-logo-enhanced.png)
│       ├── enerlab-precision-logo.webp  # Same logo, WebP (smaller; PNG is the <picture> fallback)
│       ├── favicon-16.png / favicon-32.png / apple-touch-icon.png
│       └──  (all cropped from the logo's own diamond glyph — nothing redrawn)
├── .nojekyll                # Tells GitHub Pages to serve files as-is, no Jekyll processing
└── README.md
```

No build step, no framework, no dependencies. Plain HTML/CSS, deployed as-is.

## Content status

The client has not provided company content yet. `index.html` already has
empty, ready-to-fill section anchors (`#about`, `#services`, `#contact`) and
a reserved (currently empty) legal/registration line in the footer — see the
comments in `index.html` for exactly how to activate each one once real copy
arrives. No placeholder or invented text was added anywhere.

## Local preview

Any static file server works, e.g.:

```bash
npx serve .
```

## Deployment

Hosted on **GitHub Pages**, serving from the `main` branch root.

Repo: https://github.com/eurekawebsites/enerlab-precision
Live: https://eurekawebsites.github.io/enerlab-precision/

### Moving to a custom domain later

1. Add a `CNAME` file at the repo root containing just the domain
   (e.g. `www.enerlabprecision.com`), OR set the custom domain in
   Settings → Pages → Custom domain (GitHub writes the `CNAME` file for you).
2. Point the domain's DNS at GitHub Pages (an `A`/`ALIAS` record to GitHub's
   IPs for an apex domain, or a `CNAME` record to
   `eurekawebsites.github.io` for a `www` subdomain).
3. No changes to `index.html` or asset paths are needed — every path in this
   project is relative, so it works identically under
   `/enerlab-precision/` and under a bare custom domain root.
