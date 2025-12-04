# docs/

This folder contains the static website deployed to **[vuevapor.watch](https://vuevapor.watch/)**.

## Deployment

The site is deployed via GitHub Pages from this `docs/` directory.

**Live URL:** https://vuevapor.watch/

### SSL/HTTPS Configuration

GitHub Pages provides free SSL certificates for custom domains. For HTTPS to work:

1. **DNS Configuration** - Your domain registrar must have A records pointing to GitHub's IPs:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`

2. **Enable HTTPS** - In repository Settings > Pages, check "Enforce HTTPS"

3. **Wait for provisioning** - GitHub may take up to 24 hours to provision the certificate after DNS is configured

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
