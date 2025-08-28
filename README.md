# seymourspeakers.ca

A simple "Under Construction" page for Seymour Speakers website.

## GitHub Pages Setup

This repository is configured for GitHub Pages with a custom domain (seymourspeakers.ca).

### To deploy:

1. Push your changes to the `main` branch
2. Go to your repository Settings > Pages
3. Set Source to "Deploy from a branch"
4. Select "main" branch and "/ (root)" folder
5. Save the settings

### Custom Domain Configuration:

The `CNAME` file is already configured for `seymourspeakers.ca`. You'll also need to:

1. Configure your domain's DNS settings to point to GitHub Pages
2. Add the following DNS records:
   - Type: `A` records pointing to GitHub Pages IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Type: `CNAME` record: `yourusername.github.io` (if using www subdomain)

### Files:
- `index.html` - Main page with under construction message
- `CNAME` - Custom domain configuration
- `README.md` - This file