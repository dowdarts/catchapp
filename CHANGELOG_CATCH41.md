# Catch 41 - Changelog

All notable changes to the Catch 41 Darts Practice app will be documented in this file.

## [2.0.0] - 2025-11-18

### Added
- Version metadata in HTML meta tags for tracking
- Build date timestamp in HTML headers
- HTTP cache control headers for cache-busting
- Progressive Web App (PWA) support via manifest.json
- iOS-specific PWA meta tags (apple-mobile-web-app-capable, etc.)
- Apple touch icon link
- Theme color meta tags for mobile browsers
- Version footer in UI (shows "Version 2.0.0 | Updated: Nov 18, 2025")
- Comprehensive README.md documentation
- GITHUB_PAGES_SETUP.md deployment guide
- This CHANGELOG file

### Fixed
- Removed malformed HTML content that appeared before DOCTYPE declarations
- Corrected HTML structure in both index.html and catch40withleaderboard.html
- Improved browser caching behavior to prevent old versions from being served

### Changed
- Updated manifest.json with proper PWA configuration
- Enhanced mobile responsiveness with iOS optimizations
- Preserved original Tailwind CSS README as README_TAILWIND.md

### Technical Details
- App version: 2.0.0-20251118
- Build date: 2025-11-18T16:41:55Z
- Files updated: index.html, catch40withleaderboard.html, manifest.json

## [1.0.0] - Previous Version

### Initial Features
- Practice mode for darts finishing (61-100)
- Scoring system based on dart efficiency (2-6 darts)
- Recommended takeout suggestions
- Leaderboard integration with Supabase
- Keyboard shortcuts for quick input
- Undo/Reset functionality
- Responsive design for mobile and desktop
- Pre-game modal for name entry or guest play
- Completion modal with final score

---

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).
