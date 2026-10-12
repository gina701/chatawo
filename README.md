# Cosmetics Shop Manager (PWA starter)

A free, offline-first shop management starter for one Android phone. Built with HTML, CSS, vanilla JavaScript, browser localStorage, a web app manifest and a service worker. A small Node.js web server serves the app on Render; it does not require a database.

## Features
- Product list, selling prices, stock quantities, low-stock thresholds and optional cost prices
- Sales recording with stock deduction, payment method, discount and receipt
- Expense records
- Dashboard totals for today's sales and expenses
- Print or save a receipt as PDF using the phone/browser print dialog
- JSON export and restore backup
- PWA manifest and offline cache

## Important limitations
- The records are stored only in the browser profile on the phone. They do not sync to another phone.
- Clearing browser/site data or losing the phone can lose records. Export backups regularly.
- This starter has no password login. Anyone who can open it on the phone may see the records.
- The free web address used to install the PWA may be reachable by other people who know the URL; shop records remain in local browser storage, but this is not the same as a fully secured private website.
- A PWA must be served over HTTPS (or localhost) for installation/service workers. Opening index.html directly as a file will let you preview some features but will not enable the full install/offline behavior.
- For a shop-critical system, test carefully before using it for real financial records.

## Deploy to Render
1. Push this project, including `package.json`, `server.js` and `render.yaml`, to a GitHub repository.
2. In Render, choose **New + → Blueprint** and connect the repository. Render reads `render.yaml` and creates a Node.js web service that runs `npm install` and `npm start`.
3. Wait for the web service health check to pass, then open its HTTPS `onrender.com` address in Chrome on the Android phone.

## Install on Android
1. Open the deployed HTTPS address in Chrome.
2. Tap **Install app** in the page header. If Chrome does not offer the install prompt, open Chrome's three-dot menu and choose **Install app** or **Add to Home screen**.
3. Confirm the installation and open the new app icon. It can also work offline after the first successful visit.
4. Export a JSON backup regularly and keep it somewhere safe.

This is an installable web app (PWA), not an APK from the Play Store. Users install it directly from the browser; shop records remain in that browser profile on that phone.

## Local preview
Install Node.js 18 or newer, then run `npm start` from the project folder and open `http://localhost:10000`. For proper PWA install and offline behavior, use the HTTPS Render address.
