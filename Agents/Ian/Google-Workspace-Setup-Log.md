# Google Workspace Setup Log — Ian

## Date: 2026-09-05

## Method
Used Elon's Desktop OAuth client approach (from WOR-657):

- Client secret: `/root.hermes/google_client_secret.json`
- Token: `/root.hermes/google_token.json`
- Redirect URL: `http://localhost`
- Token stored at: `/root.hermes/google_token.json` (auto-refresh enabled)
- Python venv: `/root.hermes/google_venv_ian/` (google-api-python-client installed)

## Scopes
- gmail.readonly, gmail.modify, gmail.send
- calendar, drive, spreadsheets, documents
- contacts.readonly

## Services Verified
| Service | Status | Detail |
|---------|--------|--------|
| Gmail | OK | 14 labels (INBOX, SENT, CHAT, etc.) |
| Calendar | OK | 2 calendars (johnw@workforce365.ai + UK Holidays) |
| Drive | OK | 10 files in root |

## Related Issues
- WOR-670: Initial task
- WOR-683: Asked Elon for method (answered)
- WOR-657: Elon's original setup (reference)
