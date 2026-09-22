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

The client has not provided company content yet. `index.html` still has
empty, ready-to-fill section anchors (`#about`, `#services`) and a reserved
(currently empty) legal/registration line in the footer — see the comments
in `index.html` for exactly how to activate each one once real copy arrives.
No placeholder or invented text was added anywhere.

### Contact section (active)

`#contact` ("Contáctanos") is live: a Nombre / Correo electrónico / Teléfono
/ Mensaje form with client-side validation, a single-flight submit (button
disables + shows "Enviando…" while sending), and explicit success / error
states. It styles itself from the same brand tokens and spacing system as
the rest of the page.

Submissions are relayed by [Web3Forms](https://web3forms.com) (no backend on
this static site) and delivered by email, using the same proven setup as
eurekawebsites.tech. The form carries **Enerlab's own dedicated Web3Forms
access key**; the recipient inbox is configured in the Web3Forms dashboard
for that key. The hidden `subject` / `from_name` identify submissions as
coming from the Enerlab Precision site. The provider is never named in any
visitor-facing text.

Note: Web3Forms rejects cross-origin requests from `localhost` / unknown
origins, so the live success path only works from the deployed domain — test
there, not from a local file server.

## Local preview

Any static file server works, e.g.:

```bash
npx serve .
```

## Deployment

Primary hosting is **Firebase Hosting**.

Repo: https://github.com/eurekawebsites/enerlab-precision
Firebase staging/live host: https://enerlab-precision.web.app/
Production custom domain: https://enerlab.org/ (DNS cutover to Firebase pending)

GitHub Pages remains enabled temporarily as a rollback fallback during the migration. Do not treat the old GitHub Pages URL as the canonical public URL.
