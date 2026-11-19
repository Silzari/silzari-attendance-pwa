# Silzari Attendance PWA

This repository contains the installable PWA shell for Silzari Attendance.

## Important setup

1. Keep the production attendance Apps Script and spreadsheet unchanged.
2. In the **PWA testing copy** of the Apps Script project, replace `Code.gs` with the prepared `Code.gs` from this package.
3. Deploy that testing Apps Script project as a Web app:
   - Execute as: **Me**
   - Who has access: **Anyone** (only if this is the access setting already approved for your employee PIN-based app; otherwise stop and review access requirements)
4. Copy the deployed URL ending in `/exec`.
5. In `index.html`, replace `PASTE_TEST_WEB_APP_EXEC_URL_HERE` with that exact testing `/exec` URL.
6. Upload the PWA files (but **not** `Code.gs`) to the GitHub repository and enable GitHub Pages from the `main` branch, root folder.
7. Test with a small number of test employee accounts before sharing broadly.

## Files

- `index.html`: existing attendance interface adapted to communicate with Apps Script using a hidden form/iframe bridge.
- `manifest.json`: PWA name, appearance and icons.
- `service-worker.js`: caches only the static app shell; never caches attendance data.
- `icons/`: app icons.

## Install

- Android: open the GitHub Pages URL in Chrome and choose Install app (or Chrome menu > Install app).
- iPhone: open the GitHub Pages URL in Safari > Share > Add to Home Screen.

## Important limitations

- Attendance, login, GPS verification and leave actions require an internet connection.
- GPS access must be allowed by the browser and device.
- iOS and Android PWA behaviour differs; test on actual devices.
- Do not put employee data, PIN lists, spreadsheet IDs, or private keys in this public repository.
