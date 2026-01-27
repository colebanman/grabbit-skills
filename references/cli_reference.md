# Grabbit CLI Reference

## Prereqs
- Ensure CLI is installed globally (npm): `npm i -g @cole-labs/grabbit` with `npm i -g @cole-labs/grabbit-browser`
- Or run from repo: `cd cli && pnpm dev -- <command>`
- Verify auth: `grabbit validate` (or `pnpm dev -- validate`)
- If not authed: `grabbit auth` and enter pairing code

## Browser Commands (Practical Guide)
Use these in short loops: open → snapshot → interact → snapshot → save.

- **Navigation**: `open`, `forward`, `back`, `reload`
- **Inspect page**: `snapshot` (get @refs), `get text|html|value|attr`, `is visible|enabled|checked`
- **Interact**: `click`, `dblclick`, `fill`, `type`, `press`, `select`, `hover`, `focus`, `scroll`, `scrollintoview`
- **Wait**: `wait <ms>` or `wait <selector>` (for UI changes)
- **Auth/storage**: `cookies get|set|clear`, `storage local|session`
- **Network**: `network requests [--clear]` (debug what fired)
- **HAR**: `har start|stop|export|clear` (recording control)
- **Debug**: `screenshot`, `pdf`, `console`, `errors`

Tip: `snapshot` → use `@e#` refs for stable clicks/fills.

## Troubleshooting
- **0 requests**: ensure HAR is recording; reload page.
- **403/Cloudflare**: use headed and complete challenge (optionally, instruct user to do them), then re‑save.
- **Auth errors**: rerun `grabbit auth`.
