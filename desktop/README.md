# HelixMap Desktop

Windows desktop edition of HelixMap-JS, powered by Electron.

## Download

Open the [GitHub Releases page](https://github.com/DavidH789/HelixMap-JS/releases) and download the Windows installer attached to the relevant desktop release. If no installer asset is listed, the release has not been packaged for download yet.

## Build on Windows

Requirements: a supported Node.js LTS release and npm.

1. Open a terminal in this `desktop` directory.
2. Install dependencies:
   ```powershell
   npm ci
   ```
3. Confirm `build/icono.ico` exists. The Windows installer configuration references this icon. If it is missing, copy the project's approved icon file into `build/icono.ico` before building.
4. Start the app for a local test:
   ```powershell
   npm start
   ```
5. Build the Windows installer:
   ```powershell
   npm run dist
   ```
6. Find the installer under `release/`.

## Project layout

- `main.js` — Electron main process.
- `src/` — packaged app interface and JavaScript.
- `build/icono.ico` — Windows installer/app icon required by the current build configuration.
- `package.json` / `package-lock.json` — scripts and pinned dependency tree.

Generated folders such as `node_modules/` and `release/` should not be committed. Upload the finished installer as an asset on a GitHub Release instead of adding the large installer to the source tree.

## Privacy and safety

Do not include personal raw DNA files, exported personal results, credentials, tokens, or private configuration in a public build or repository. HelixMap is an exploratory model and is not a medical or forensic tool.

## License

The desktop wrapper is marked MIT in `package.json`. Review third-party dependency and data notices before distributing a release.
