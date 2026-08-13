# psychard.com

The family landing page. One static HTML file, one stylesheet, a folder of
icons. No build step, no dependencies, nothing to install.

## Adding a game

1. Drop a **square** PNG into `icons/`. 180×180 is plenty — the page shows it at
   72px, so 180 covers a retina screen with room to spare.
2. Open `index.html`, find the `<!-- to add a game -->` comment, copy one `<li>`
   block, and change the link, icon path, name and description.


## Deploys

Push to `main` and it is live in about a minute. 
`.github/workflows/deploy.yml` publishes the repo root to GitHub Pages on every
push to `main`.

