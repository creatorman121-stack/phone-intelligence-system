# OceanJet PortDesk V137 Season 8 – Admin Remote Config Command

## What changed

This package keeps the existing single-file `index.html` GitHub Pages app, preserves the V134.1 Native Storage Bridge, and adds the V135 Season 6 Futuristic Ops Cockpit.

The app now detects its environment automatically:

1. Capacitor Android + Filesystem plugin when running as a native wrapper.
2. IndexedDB fallback when running on GitHub Pages or normal browser.
3. localStorage emergency fallback for compatibility.


## Professional stabilization pass

- Removed the old AR Scanner module and TensorFlow/COCO-SSD scripts because AR was removed in V125.
- Removed unrelated Meta Playables SDK/touch-patch code that could interfere with normal GitHub Pages or Android wrapper behavior.
- Fixed duplicate Admin drawer entry for supervisor mode.
- Hardened database parsing so corrupted localStorage data does not break startup.
- Hardened save flow so IndexedDB/native storage can still work if localStorage quota fails.
- Improved Capacitor backup sharing by using the native file URI returned by Filesystem.writeFile.
- Added offline-safe Live Map fallback if Leaflet CDN is unavailable.
- Added before-unload autosave protection.
- Rechecked duplicate IDs/functions and JavaScript syntax.

## GitHub Pages usage

Upload `index.html` to your GitHub Pages repository as usual.

The new **Storage / Backup** drawer item provides:

- Storage status
- Last auto-save
- Backup size
- Backup to phone/download
- Restore from JSON backup
- Storage health check
- Temporary cache clear

## Android wrapper setup

Install Node.js, Android Studio, then run:

```bash
npm install
npx cap init OceanJetPortDesk com.oceanjet.portdesk --web-dir .
npx cap add android
npx cap sync android
npx cap open android
```

Build the APK from Android Studio.

## Storage notes

Native Capacitor mode writes OceanJet backups under app-accessible Documents storage using the Capacitor Filesystem plugin when available. Browser mode does not crash and uses IndexedDB plus JSON downloads.

## Important preservation notes

- Existing baggage calculator logic was not replaced.
- Existing schedules and fare database were preserved.
- Existing receipt/history/admin flow was preserved.
- AR Scanner remains removed as required by the V125+ project direction.
- Broken bottom-safe nav injection was removed because the app requirement says no bottom tab.

## V135 Season 6 – Futuristic Ops Cockpit

Built on V134.1 Professional Stabilized. This update adds a safe Season 6 HUD without replacing the existing baggage calculator or storage bridge.

### Added
- Season 6 HUD drawer module
- Advanced cockpit health gauge and next-boarding intelligence
- Pseudo-3D route heatmap based on local transaction activity
- Staff performance goals and unlockable badges
- Passenger mobile dashboard with boarding preview and advisory feed
- Environmental planning estimates for fuel impact, CO2, and baggage efficiency
- Lite Mode toggle for low-end Android phones

### Preserved
- Existing baggage calculator logic
- V134.1 native/IndexedDB/localStorage storage bridge
- GitHub Pages browser fallback
- Capacitor Android wrapper compatibility



## V136 Season 7 – Passenger Intelligence Command Center

Built on V135 Season 6 and the V134.1 Professional Storage Bridge. This update adds a practical intelligence layer for passenger handling and shift operations while preserving the baggage calculator, schedules, receipts, storage bridge, and Android/GitHub Pages compatibility.

### Added
- Season 7 Intel drawer module
- Passenger Journey Center with route status, baggage tracker, fare guide, and “What Should Passenger Do Now?” guidance
- Passenger Status Board for waiting, boarding, boarded, missed, and delayed records
- Auto-Assist Operations Panel that detects the next vessel from local schedules
- Delay Advisory Generator with copy-ready staff/passenger notice text
- Smart Schedule Engine 2.0 with boarding status timeline, recently departed logic, and connection hints
- Storage Health Upgrade with database size estimate, backup shortcut, health check, report-cache cleanup, and safe restore preview before import
- Passenger Alert Feed and Route Pressure Board

### Preserved
- Existing baggage calculator logic and fare slabs
- Existing route schedules and receipt/history flow
- V135 Futuristic Ops Cockpit
- V134.1 Native Storage Bridge and browser fallback behavior
- GitHub Pages single-file `index.html` support
- Capacitor Android wrapper starter files


## V137 Season 8 – Admin Remote Config Command

Built from the clean V136 source with a professional admin-only remote configuration module.

### Added
- Supervisor-only Config Center drawer module.
- Remote JSON manifest support or base URL + category files.
- Offline cache through OceanJetStorageBridge, IndexedDB, and local fallback.
- Safe preview and validation before applying fares, slabs, schedules, vessels, routes, or advisories.
- Fare and schedule version labels, last fetched/applied status, and route/trip counts.
- Current config export and sample manifest export.
- Built-in restore option with automatic snapshot before applying changes.

### Supported config fields
```json
{
  "version": "June-8-Fares-and-Schedule",
  "fareVersion": "June 8 Fare Update",
  "scheduleVersion": "Schedule 2026-06",
  "fares": {},
  "slabs": {},
  "schedules": {},
  "vessels": {},
  "routes": {},
  "advisories": []
}
```

### Safety notes
- The old baggage calculator logic is not replaced.
- Remote config is applied only after validation.
- Supervisor mode is required to edit/apply config.
- GitHub Pages remains fully usable; remote JSON is optional.
