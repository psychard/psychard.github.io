# psychard.com

The family landing page. One static HTML file, one stylesheet, a folder of
icons. No build step, no dependencies, nothing to install.

## Adding a game

Two things:

1. Drop a **square** PNG into `icons/`. 180×180 is plenty — the page shows it at
   72px, so 180 covers a retina screen with room to spare.
2. Open `index.html`, find the `<!-- to add a game -->` comment, copy one `<li>`
   block, and change the link, icon path, name and description.

Push to `main` and it is live in about a minute. The grid reflows on its own —
there is no per-game CSS and no list to keep in sync anywhere else.

## Where the icons came from

| File | Source |
| --- | --- |
| `climb.png` | Hand-drawn placeholder, in the game's own palette (`src/tuning.js` in [stickman-climb](https://github.com/psychard/stickman-climb)). **Worth replacing with something better.** |
| `scales.png` | `public/icon-512.png` from [scales-tuner](https://github.com/rwest/scales-tuner), downscaled |
| `cycle-blaster.png`, `office-hop.png`, `tritave.png` | The `apple-touch-icon` embedded in each game's HTML in [Cell-blaster](https://github.com/psycheloui/Cell-blaster) |
| `psychard.svg`, `favicon-32.png`, `apple-touch-icon.png` | The site's own `P` mark |
| `og.png` | Link-preview card, 1200×630 |

These are **copies**, not links to the other repos — a cross-repo
`raw.githubusercontent.com` reference is slow and breaks silently. If a game
changes its icon, refresh the copy here.

## Deploys

`.github/workflows/deploy.yml` publishes the repo root to GitHub Pages on every
push to `main`. The Pages source is set to "GitHub Actions", not a branch, so
there is no Jekyll build involved — files are served exactly as committed.

## Domain

`CNAME` holds the custom domain. DNS is at GoDaddy, and there is a wildcard
`*.psychard.com → psychard.github.io` record, which is how `climb.psychard.com`
works from its own repo.

Note that `scales.psychard.com` resolves but 404s: the wildcard points it here,
but `scales-tuner` lives under `rwest`, so no repo claims that hostname. To fix,
move the repo into the `psychard` org and give it a `CNAME`.

## History

Everything before the 2026 rewrite — the 2011 wedding site and the 2015 baby
announcement — is at the `wedding-site-2015` tag.
