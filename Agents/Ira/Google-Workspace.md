# Ira's Google Workspace Setup

## Status
- **Setup completed**: 2026-09-05
- **Token location**: `/root/.hermes/google_token.json`
- **Profile**: ira
- **Permissions**: Gmail (read, send, modify), Calendar, Drive, Contacts, Sheets, Docs

## Verification
- Gmail: Can search, read, send, modify labels
- Calendar: Can list and create events
- Drive: Can search, upload, create folders, share, delete
- Sheets: Can create, read, write, append
- Docs: Can create, read, append
- Contacts: Can list contacts

## Notes
- The token is shared at the `~/.hermes/` level (not profile-specific).
- Profile-specific Python venv created at `/root/.hermes/.venv-google/` with required deps.
