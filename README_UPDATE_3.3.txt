PAK GSM REPAIR UPDATE 3.3

This release upgrades the 3.1 build without changing the existing cloud key or device data format.

MAIN IMPROVEMENTS
- App title/version: Pak GSM Repair Update 3.3
- Uses the current Apps Script Web App URL configured in cloud-config.js.
- Automatic cloud backup remains ON by default and retries pending backups after connectivity returns.
- Cloud history now keeps an immutable timestamped snapshot for every successful backup, plus a daily snapshot.
- Timestamped history is bounded to the newest 200 snapshots per device to prevent unlimited Drive growth.
- Before a restore, the current device state is backed up to cloud when possible, creating a safety point before replacement.
- Products are now included in backup payloads and restored with customer data, File Vault and photos.
- Saving/deleting products marks cloud backup pending so the catalog is protected by automatic backup.
- Added PWA manifest, icons and service worker files for later HTTPS hosting and PWABuilder packaging.
- Standalone app metadata is prepared so an Android package can open without a normal browser address bar when the PWA is hosted correctly.

CLOUD SERVER ONE-TIME UPDATE
Replace the existing Apps Script Code.gs with this release's Code.gs and redeploy/update the Web App.
Execute as: Me / owner
Who has access: Anyone

CURRENT WEB APP URL
https://script.google.com/macros/s/AKfycby_v5hX2G1OLBNdNvjxrtlWtqSijQ9RCDxQD0znDqaT5dF3YaKaxAUdo0q2n_-ihny2Ow/exec

PWA / APK NOTE
The included manifest.json, sw.js and icons are ready for PWA hosting, but PWABuilder needs a public HTTPS URL. The content:// address used by a local APK/web wrapper cannot be submitted directly to PWABuilder.


APP UPDATE SYSTEM
- The app now checks ./update.json for a newer version.
- Future web-app updates can be delivered by replacing the hosted web files and incrementing the Service Worker cache version.
- A compatible APK/TWA normally does not need to be rebuilt for ordinary HTML/CSS/JS/data-feature updates because it loads the hosted PWA.
- Native Android/TWA configuration changes still require a new Android build.
- Keep the same Android signing key for future APK/AAB releases.


FINAL AUDIT NOTE:
- Added a quiet background update check after app startup; it does not block startup and does not alter local customer data.
- Strengthened the PWA manifest with a stable app id, display override, and categories for packaging/discovery.
