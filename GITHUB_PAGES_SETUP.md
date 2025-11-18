# GitHub Pages Setup Guide

This guide explains how to configure GitHub Pages for the Catch 41 Darts Practice app.

## Setting Up GitHub Pages

### Method 1: Via GitHub Web Interface (Recommended)

1. Go to your repository on GitHub: `https://github.com/dowdarts/catchapp`
2. Click on **Settings** (top navigation)
3. Scroll down to **Pages** section in the left sidebar
4. Under **Source**, select the branch you want to deploy (e.g., `main` or `copilot/republish-gitpage`)
5. Select the root folder `/` as the directory
6. Click **Save**
7. GitHub will provide you with a URL where your site is published (usually `https://dowdarts.github.io/catchapp/`)

### Method 2: Via GitHub Actions Workflow

Create a `.github/workflows/deploy.yml` file with the following content:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      
      - name: Setup Pages
        uses: actions/configure-pages@v4
      
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## What's Included in This Version (2.0.0)

### Cache-Busting Features
- HTTP cache control meta tags to force browsers to reload
- Version metadata in HTML headers
- Build date timestamp

### PWA (Progressive Web App) Support
- `manifest.json` file for installable web app
- Theme colors for mobile browsers
- Apple touch icon support
- Standalone display mode

### Version Visibility
- Version number displayed in the UI footer
- Build date visible to users

## Verifying the Deployment

After setting up GitHub Pages:

1. Wait 1-2 minutes for GitHub to build and deploy
2. Visit your GitHub Pages URL
3. Check the browser console for any errors
4. Verify the version footer shows "Version 2.0.0"
5. Test on mobile devices to ensure responsive design works

## Forcing Users to Get the New Version

Users who have cached the old version can force reload by:
- **Windows/Linux**: Press `Ctrl + Shift + R` or `Ctrl + F5`
- **Mac**: Press `Cmd + Shift + R`
- **Mobile**: Clear browser cache or use private/incognito mode

The cache-busting meta tags added in this version will help prevent future caching issues.

## Custom Domain (Optional)

If you want to use a custom domain:

1. Go to Settings > Pages
2. Enter your custom domain in the "Custom domain" field
3. Configure your DNS provider to point to GitHub Pages:
   - Add a CNAME record pointing to `dowdarts.github.io`
4. Enable "Enforce HTTPS" option

## Troubleshooting

### Page not loading
- Check that GitHub Pages is enabled in repository settings
- Verify the correct branch is selected
- Ensure `index.html` is in the root of the selected directory

### Old version showing
- Hard refresh the page (Ctrl+Shift+R)
- Clear browser cache
- Try in private/incognito mode

### Images not loading
- Verify image files are committed to the repository
- Check image paths in HTML (use relative paths: `./image.png`)
- Ensure files are not in `.gitignore`

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Progressive Web Apps (PWA) Guide](https://web.dev/progressive-web-apps/)
