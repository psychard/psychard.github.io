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
(Tilt Ball) and `arboretum/` (The Painted Arboretum) are the two. Anything
needing a phone sensor (motion, camera, mic) has to be served over HTTPS, which
this domain is, so hosting it here is the easy route.

Each of those folders is self-contained: one `index.html`, a `manifest.json` so
it can be installed to a home screen, and a `vendor/` folder for anything it
would otherwise fetch from someone else's CDN. The arboretum carries three.js
(MIT) and the Architects Daughter typeface (SIL Open Font License) that way, so
the game keeps working offline and makes no third-party requests.

## Deploys

Push to `main` and it is live in about a minute. 
`.github/workflows/deploy.yml` publishes the repo root to GitHub Pages on every
push to `main`.

