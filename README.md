# [psychard.com](https://psychard.com/)

The family landing page. One static HTML file, one stylesheet, a folder of
icons. No build step, no dependencies, nothing to install.

## Adding a game

1. Drop a **square** PNG into `icons/`. 180×180 is plenty — the page shows it at
   72px, so 180 covers a retina screen with room to spare.
2. Open `index.html`, find the `<!-- to add a game -->` comment, copy one `<li>`
   block, and change the link, icon path, name and description.


## Apps hosted here

Some games live in this repo rather than elsewhere: a folder with an
`index.html` inside, served at `https://www.psychard.com/<folder>/`. `tilt/`
(Tilt Ball) is the one. Anything needing a phone sensor (motion, camera, mic)
has to be served over HTTPS, which this domain is, so hosting it here is the
easy route.

Such a folder is self-contained: one `index.html`, a `manifest.json` so it can
be installed to a home screen, and, if it needs one, a `vendor/` folder for
anything it would otherwise fetch from someone else's CDN.

A game that outgrows a folder can move to its own repo and a subdomain, as
The Painted Arboretum did: it lives in
[psychard/arboretum](https://github.com/psychard/arboretum) and is served at
[arboretum.psychard.com](https://arboretum.psychard.com/). Only its card icon,
`icons/arboretum.png`, stays here.

## Deploys

Push to `main` and it is live in about a minute. 
`.github/workflows/deploy.yml` publishes the repo root to GitHub Pages on every
push to `main`.

