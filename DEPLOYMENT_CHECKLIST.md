# Deployment Checklist for GitHub Pages

## Pre-Deployment Steps

- [x] Fixed HTML structure (removed malformed content)
- [x] Added version metadata and cache-busting headers
- [x] Created manifest.json for PWA support
- [x] Added version footer to UI
- [x] Created comprehensive documentation
- [x] Tested locally via HTTP server

## GitHub Pages Setup Steps

### Option 1: Deploy from This Branch (Recommended)

1. **Navigate to Repository Settings**
   - Go to: https://github.com/dowdarts/catchapp/settings/pages

2. **Configure Source**
   - Under "Build and deployment" → "Source"
   - Select: **Deploy from a branch**
   - Branch: `copilot/republish-gitpage` or `main` (choose the branch with these changes)
   - Folder: `/ (root)`
   - Click **Save**

3. **Wait for Deployment**
   - GitHub will automatically build and deploy
   - This usually takes 1-2 minutes
   - Check the Actions tab to monitor progress

4. **Access Your App**
   - Your app will be available at: https://dowdarts.github.io/catchapp/
   - The URL will be displayed on the Pages settings page

### Option 2: Merge to Main and Deploy

1. **Merge this PR to main branch**
   - Review and approve this PR
   - Merge to main

2. **Configure GitHub Pages**
   - Go to Settings → Pages
   - Select `main` branch
   - Select `/ (root)` folder
   - Save

3. **Deployment Complete**
   - App will deploy automatically

## Post-Deployment Verification

### Test These Features:
- [ ] App loads correctly
- [ ] Version footer shows "Version 2.0.0"
- [ ] Leaderboard loads (check network tab for Supabase calls)
- [ ] Game functionality works (try recording a score)
- [ ] Keyboard shortcuts work (0, 2-6, Backspace)
- [ ] Undo button works
- [ ] Reset button shows confirmation modal
- [ ] Mobile responsiveness (test on phone)
- [ ] PWA install prompt appears on mobile Chrome/Safari

### Browser Cache Testing:
Test in multiple scenarios:
- [ ] Fresh incognito/private window
- [ ] After hard refresh (Ctrl+Shift+R)
- [ ] On mobile device
- [ ] After clearing browser cache

## Troubleshooting

### If app doesn't load:
1. Check GitHub Pages is enabled in Settings
2. Verify correct branch is selected
3. Check Actions tab for deployment errors
4. Wait 5 minutes and try again

### If old version shows:
1. Hard refresh: Ctrl+Shift+R (Windows/Linux) or Cmd+Shift+R (Mac)
2. Clear browser cache
3. Try incognito/private mode
4. The cache-busting headers should prevent this issue

### If images don't load:
1. Check that image files are committed (catch40applogo.png, CGC official logo-1.png)
2. Verify paths are correct in HTML
3. Check browser console for 404 errors

## Updating the App in the Future

When making changes and wanting users to get the latest version:

1. **Update version numbers:**
   - Both HTML files: meta tags and footer
   - manifest.json: version field
   - CHANGELOG_CATCH41.md: add new entry

2. **Update build date:**
   - Both HTML files: `<meta name="build-date" content="...">`

3. **Commit and push changes**

4. **Users will need to:**
   - Hard refresh (Ctrl+Shift+R)
   - Or clear cache
   - Cache-busting headers help, but not all browsers respect them

## Custom Domain (Optional)

If you want to use a custom domain:

1. **In GitHub Settings → Pages:**
   - Enter custom domain (e.g., catch41.example.com)
   - Save

2. **In DNS Provider:**
   - Add CNAME record pointing to: dowdarts.github.io
   - Wait for DNS propagation (can take up to 24 hours)

3. **Enable HTTPS:**
   - GitHub will automatically provision SSL certificate
   - Check "Enforce HTTPS" once certificate is ready

## Security Notes

- The Supabase credentials in the HTML are public (anon key)
- This is expected for frontend apps
- Backend security is handled by Row Level Security (RLS) in Supabase
- No sensitive data is exposed in the code

## Support

For issues:
- Check GITHUB_PAGES_SETUP.md for detailed instructions
- Review GitHub Pages documentation
- Open an issue on the repository

---

**Last Updated:** 2025-11-18  
**Version:** 2.0.0
