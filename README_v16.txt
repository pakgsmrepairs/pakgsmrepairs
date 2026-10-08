Pak GSM Repair Pro v16

WHAT CHANGED
- Removed client-side Google OAuth / Google account login flow.
- Replaced it with owner-controlled Cloud Backup.
- Client phones do not need a Gmail login, OAuth Client ID, or Google Drive permission.
- Backup/restore goes through a Google Apps Script backend that stores each device backup in the app owner's Google Drive.
- File Vault and Client Data pages remain in the app.
- Settings remains responsive/full-width on mobile.

ONE-TIME OWNER SETUP
1. Open script.google.com in the Google account that should own the backups.
2. Create an Apps Script project and paste Code.gs.
3. Run setupCloudFolder once and approve Drive permission.
4. Deploy as Web app: Execute as Me; Who has access: Anyone.
5. Copy the /exec URL into cloud-config.js as PGR_CLOUD_BACKUP_URL.
6. Keep the same PGR_CLOUD_BACKUP_KEY as the CLOUD_KEY in Code.gs.
7. Open index.html.

The client only sees Cloud Backup / Restore buttons. OAuth and Client ID are not shown.
See SETUP_CLOUD_BACKUP.txt for the exact deployment steps and security notes.
