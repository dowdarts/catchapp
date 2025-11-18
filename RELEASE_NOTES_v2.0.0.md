# Release Notes - Catch 41 v2.0.0

**Release Date:** November 18, 2025  
**Version:** 2.0.0-20251118

## 🎉 What's New

This major release prepares the Catch 41 Darts Practice app for proper GitHub Pages deployment and ensures users always get the latest version.

## 🔧 Major Changes

### 1. Fixed HTML Structure
**Problem:** HTML files contained malformed content before the DOCTYPE declaration  
**Solution:** Removed 18 lines of invalid content from both index.html and catch40withleaderboard.html  
**Impact:** Cleaner, standards-compliant HTML that validates properly

### 2. Version Management System
**New Features:**
- Version metadata in HTML headers (2.0.0)
- Build timestamp (2025-11-18T16:41:55Z)
- Visible version footer in the UI
- CHANGELOG_CATCH41.md for tracking changes

**Benefits:**
- Users can verify they have the latest version
- Easier troubleshooting and support
- Clear version history

### 3. Cache-Busting Implementation
**Problem:** Browsers cache old versions of the app  
**Solution:** Added HTTP cache control headers:
```html
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Expires" content="0">
```

**Impact:** Browsers will always request the latest version from the server

### 4. Progressive Web App (PWA) Support
**New Features:**
- manifest.json with app metadata
- iOS-specific PWA tags
- Apple touch icon support
- Standalone display mode
- Theme colors for mobile browsers

**Benefits:**
- Users can install the app on their devices
- Works offline after first load
- Native app-like experience on mobile
- Add to home screen functionality

### 5. Comprehensive Documentation
**New Files:**
- `README.md` - Main app documentation
- `GITHUB_PAGES_SETUP.md` - Detailed deployment guide
- `DEPLOYMENT_CHECKLIST.md` - Quick deployment reference
- `CHANGELOG_CATCH41.md` - Version history
- `RELEASE_NOTES_v2.0.0.md` - This file

**Benefits:**
- Easy deployment for repository maintainers
- Clear instructions for troubleshooting
- Documentation for future updates

## 📋 Technical Details

### Files Modified
- ✅ `index.html` (18 lines removed, 10 lines added)
- ✅ `catch40withleaderboard.html` (18 lines removed, 10 lines added)

### Files Created
- ✅ `manifest.json` - PWA configuration
- ✅ `README.md` - App documentation
- ✅ `GITHUB_PAGES_SETUP.md` - Deployment guide
- ✅ `DEPLOYMENT_CHECKLIST.md` - Quick reference
- ✅ `CHANGELOG_CATCH41.md` - Version history
- ✅ `RELEASE_NOTES_v2.0.0.md` - This file

### Dependencies
- No new dependencies added
- Uses existing libraries: Tailwind CSS, Supabase JS Client

## 🚀 Deployment Instructions

### For Repository Owners:

1. **Merge this PR** to the main branch

2. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` (or `copilot/republish-gitpage`)
   - Directory: `/ (root)`
   - Click Save

3. **Wait for deployment:**
   - Check Actions tab for progress
   - Usually takes 1-2 minutes
   - App will be at: https://dowdarts.github.io/catchapp/

4. **Verify deployment:**
   - Open the URL
   - Check that version shows "2.0.0"
   - Test functionality (score entry, leaderboard, etc.)

### For Users:

If you've visited the app before and see an old version:

**Desktop:**
- Windows/Linux: Press `Ctrl + Shift + R`
- Mac: Press `Cmd + Shift + R`
- Or clear your browser cache

**Mobile:**
- Clear browser cache
- Use private/incognito mode
- Or uninstall and reinstall the PWA

## 🧪 Testing Checklist

After deployment, verify these features:

- [ ] App loads without errors
- [ ] Version footer displays "Version 2.0.0"
- [ ] Leaderboard loads and displays scores
- [ ] Score entry works (2, 3, 4, 5, 6, 0 buttons)
- [ ] Keyboard shortcuts work (0-6, Backspace)
- [ ] Undo button functions correctly
- [ ] Reset button shows confirmation modal
- [ ] Game completion modal appears after 40 outs
- [ ] Mobile responsive design works
- [ ] PWA install prompt appears (mobile Chrome/Safari)

## 🐛 Known Issues

None at this time.

## 🔮 Future Enhancements

Potential features for future versions:
- Service worker for better offline support
- Practice history tracking
- Multiple game modes
- Statistics and analytics
- Social sharing features
- Custom out ranges
- Dark mode theme

## 📞 Support

For issues or questions:
- Check the [README.md](./README.md) for basic usage
- Review [GITHUB_PAGES_SETUP.md](./GITHUB_PAGES_SETUP.md) for deployment help
- Check [DEPLOYMENT_CHECKLIST.md](./DEPLOYMENT_CHECKLIST.md) for quick reference
- Open an issue on GitHub

## 👥 Contributors

This release was prepared by GitHub Copilot in collaboration with the repository owner.

## 📜 License

See [LICENSE](./LICENSE) file for details.

---

**Thank you for using Catch 41! Happy practicing! 🎯**
