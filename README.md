# UCAPS Emergency Phone Testing

Field testing app and admin console for the campus emergency phones.

| Page | URL path | Who |
|---|---|---|
| Testing app (mobile) | `/` | approved testers and UCAPS staff |
| Admin console | `/admin/` | UCAPS admins only |

## Where the data lives
Nothing about the phones is stored in this repo. The roster, test results and accounts live in
Supabase (project `ucaps-tools`) behind row-level security: `ep_phones` (locations, readable by testers),
`ep_phone_details` (extensions, models, notes: admins only) and the shared `ucaps_users` account list.
`schema.sql` documents the tables and rules. **Never commit extensions, IP/MAC addresses or install notes here.**

## Sign-in
Email one-time code (or link) to an address on the approved list. Testers are added in the admin console, Testers tab.

## Publish (GitHub Pages)
Settings, Pages, Source: `main` branch, `/ (root)`. Then in Supabase, Authentication, URL Configuration, add
`https://paulop1980.github.io/emergency-phone-testing/**` to Redirect URLs.
