---
feature: access-management
status: prototype
owner: design
---

## Design decisions

- Add, edit and delete open as dialogs on the list page, not as separate pages (DESIGN.md, dialog use).
- Status is a dot plus text ("Active", "Invitation pending"). Colour is never the only signal.
- Roles: Data viewer, Data collector, Data validator, Admin. Super admin is a global role and is not set from a site. The role filter shows what the selected role can do.
- Long names and emails are cut off with an ellipsis and shown in full on hover.

## Interaction decisions

- Errors show under the field they belong to and clear when the field is edited.
- After saving, the dialog closes and a toast confirms.
- Delete names the user and says it cannot be undone.
- Resend invitation is only shown for pending invitations.
- Rows do not react to hover or click. Only the action buttons do.

## Rationale

- One list with search and one filter is enough for the expected number of users per site.
- The same patterns as the other settings screens keep behaviour consistent.

## Alternatives considered

- A separate page for edit user. Dropped: dialogs are the agreed pattern.

## Open questions

- Should an admin be able to change their own role?
- Should deleting a user with records need a transfer of ownership first?
- Should the user count ("Currently there are N users") stay?

## Changelog

- 2026-11-18: First version of the prototype page.
- 2026-11-18: Logo in top bar. "(required)" on the invite and edit fields, red border on invalid dropdowns, email read-only when editing. Added dialogs, messages and logo to the changes table.
- 2026-11-18: Two-line logo in the top bar, logo file added in assets.
- 2026-11-19: Super admin removed from the roles. Organization is optional. Dialogs no longer close when clicking outside. Toast icon colour is now the token `--good-on-dark` (added to tokens.json in delta-design pull request 1). Added requirements.md.
- 2026-11-19: Dialogs close only with Cancel, the close button or Escape (not on outside click). Documented in the changes table.
- 2026-11-19: Backend section corrected. Search across name, email and organization, and sorting of the whole list need server changes. Earlier text said no backend changes.
- 2026-11-19: Edit user dialog shows status, date added and added by as read-only lines. User count removed (pagination shows the total).
