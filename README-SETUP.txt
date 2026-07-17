# Unity Pads website — GitHub Pages setup

This folder contains the complete Unity Pads website.

## Important image note

The supplied Alamy image was not included because it contains visible stock-library watermarks.
Only use that image if you purchase the appropriate licence and download the unwatermarked file.
You should also make sure you have permission to publish every other supplied photograph.

## Folder contents

- `index.html` — the main website
- `privacy.html` — privacy information
- `404.html` — page-not-found page
- `assets/styles.css` — all styling
- `assets/script.js` — navigation, animation and contact-form behaviour
- `assets/images/` — logo and website images
- `CNAME` — connects the site to unitypads.co.uk
- `.nojekyll` — tells GitHub Pages to serve the static files directly

## Quick local preview

Double-click `index.html`. It should open in your browser.

A browser may restrict a small amount of local behaviour, but the design, images and navigation should still be visible.

## GitHub upload

Create a public GitHub repository called `unity-pads-website`.

Upload the CONTENTS of this folder to the repository. `index.html` must be visible at the repository's top level.

## GitHub Pages publishing

Open the repository:
Settings → Pages → Build and deployment

Choose:
- Source: Deploy from a branch
- Branch: main
- Folder: / (root)

Save, then wait for GitHub to publish the site.

## Custom domain

In Settings → Pages, enter:

unitypads.co.uk

The included CNAME file contains the same domain.

## GoDaddy DNS

In GoDaddy DNS management, remove only conflicting parked-domain website records. Do not remove MX or email-related TXT records.

Add these A records:

@ → 185.199.108.153
@ → 185.199.109.153
@ → 185.199.110.153
@ → 185.199.111.153

Add this CNAME:

www → YOUR-GITHUB-USERNAME.github.io

Replace YOUR-GITHUB-USERNAME with your actual GitHub username.

Return to GitHub Pages after DNS propagation and enable Enforce HTTPS.

## Contact form

GitHub Pages is static and cannot process a form on its own. The included form creates a prepared email to unitypads@outlook.com in the visitor's email application.

The direct email and telephone links remain available even when the visitor does not use the form.
