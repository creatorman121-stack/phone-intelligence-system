# OceanJet PortDesk APK Build on Phone + GitHub

## Important files

Make sure these files are in your GitHub repository root:

- `index.html`
- `package.json`
- `capacitor.config.json`
- `www/index.html`
- `.github/workflows/build-apk.yml`

## How to run

1. Open your repository on GitHub.
2. Go to **Actions**.
3. Open **Build Android APK**.
4. Tap **Run workflow**.
5. Wait until it finishes.
6. Open the completed run.
7. Scroll to **Artifacts**.
8. Download **OceanJet-PortDesk-Debug-APK**.
9. Extract it and install `app-debug.apk` on your Android phone.

## Why this fixed package is different

- Capacitor now uses `www/` instead of the repository root.
- The workflow sets up Java 17.
- The workflow uses Node 22.
- Gradle executable permission is fixed before build.
- APK upload uses `actions/upload-artifact@v4`.
