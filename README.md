# MSI Ticketing – Updates

This repo only hosts **GitHub Releases** for the MSI Ticketing desktop app (Electron auto-updates).

## How to publish a new version
1. Bump version in `package.json` (e.g., 1.0.4).
2. Build: `npm run dist`  
   Files created in `release/`:
   - `MSI Ticketing Setup X.Y.Z.exe`
   - `MSI Ticketing Setup X.Y.Z.exe.blockmap`
   - `latest.yml`
3. Draft a GitHub Release:
   - Tag: `vX.Y.Z` (create if needed), Title: `X.Y.Z`
   - Upload the three files above as **Assets** (don’t rename).
   - Publish.

## App side (already wired)
- Uses `electron-updater` with:
  ```js
  const { autoUpdater } = require('electron-updater');
  autoUpdater.checkForUpdatesAndNotify();
