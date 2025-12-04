# docs/

This folder contains the static website deployed to **[vuevapor.watch](http://vuevapor.watch/)**.

## Deployment

The site is deployed via GitHub Pages from this `docs/` directory.

**Live URL:** http://vuevapor.watch/

## Contents

| File | Purpose |
|------|---------|
| `index.html` | Main page with live benchmark data |
| `styles.css` | Styling |
| `favicon.svg` | Site icon |
| `CNAME` | Custom domain configuration |

## How It Works

The website fetches benchmark data directly from the repository's `benchmark/results/build-history.json` file. No build step is required - it's a static site that pulls live data on page load.

## Local Development

Open `index.html` in a browser. Note that benchmark data fetching requires an internet connection to reach the GitHub raw content URL.
