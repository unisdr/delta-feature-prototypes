---
feature: access-management
status: prototype
owner: design
---

## Design decisions

- Add, edit and delete open as dialogs on the list page, not as separate pages (DESIGN.md, dialog use).
- Status is a dot plus text ("Active", "Invitation pending"). Colour is never the only signal.
- Roles: Data viewer, Data collector, Data validator, Admin, Super admin. The role filter shows what the selected role can do.
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
