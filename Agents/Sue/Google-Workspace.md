# Sue — Google Workspace Setup

## Status
- **Setup completed**: 2026-09-09
- **Method**: Shared OAuth 2.0 token (from Elon's Desktop OAuth client)
- **Token location**: `/root/.hermes/google_token.json` (shared)
- **Client secret**: `/root/.hermes/google_client_secret.json`
- **Profile**: sue
- **Python venv**: `/root/.hermes/google_venv_sue/`
- **Permissions**: Gmail (read, send, modify), Calendar, Drive, Contacts, Sheets, Docs

## Verification
| Service | Status | Detail |
|---------|--------|--------|
| Gmail | OK | 5 unread messages retrieved |
| Calendar | OK | Accessible (no upcoming events in range) |
| Drive | OK | 10+ files listed, search working |

## Notes
- Token is shared at `~/.hermes/` level (not profile-specific)
- Used `uv` to create venv since `python3 -m venv` was missing `ensurepip`
- Same Google Cloud project as all other agents (`rich-operand-507017-i4`)
- Full PA workflow ready: email triage, calendar management, document handling
