# Access management

Prototype of the Access management screen in DELTA (Settings, Access management). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/access-management/

## Purpose

Let administrators invite people to a site and set what they can do on it.

## Users

- Admins who manage access for one site.

## Scope

- User list with search and a role filter.
- Sorting on name, status, organization, role and date added. Sorting applies to the whole list.
- Pagination with a rows per page choice.
- Invite user, edit user and delete user as dialogs on the list page.
- Resend invitation for users whose invitation is pending.

## Not in scope

- Real data and sign-in. All users and organizations are example data.
- Permissions per feature beyond the four roles.

## Changes from the current version

Compared with the current Access management page in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Finding users | Organization filter (typed name) and role filter | One search box for name, email and organization, plus the role filter | Users are found by name or email more often than by organization |
| Sorting | None | Click a column header to sort | Needed to find the newest or pending users |
| Rows per page | 10, 20, 30, 40, 50 | 25, 50, 100, default 25 | Design system standard for tables |
| Status | Status column plus a "Status legend" section | Dot plus text in the status column, no legend | The text carries the meaning, so no legend is needed |
| User count | "Currently there are N users in the system." | Not shown | To be decided |
| Role names | Data Viewer, Data Collector, Data Validator | Data viewer, Data collector, Data validator | Sentence case |
| Add, edit, delete, resend | Each opens as a separate page or overlay with its own address | Invite and edit user and delete confirmation open as dialogs over the list; the list stays in place | Fewer page loads, the user keeps their place in the list |
| Invite user dialog | Title "Add user" on the page, "Invite User" as button, field labels without a required marker, placeholder "Enter Email" | Title "Invite user", "(required)" on email and role, none on organization, email placeholder "name@organization.org" | Required fields are stated before the user submits |
| Form errors | Email error only | Error text under each empty or invalid field (email, role), red border on the field, shown on submit and cleared when the user changes the field | Every required field gets feedback |
| Role description | "You have selected [role]" and "A {role} is able to:" | One line under the role field: "A data collector can ..." | Shorter, same information |
| Edit user | Email is read-only; page also shows account status, date added and added by | Email is read-only; status and date added are in the list, "added by" is not shown | To be decided |
| Delete confirmation | "Are you sure you want to delete this user?" and "This data cannot be recovered after being deleted." | "Delete user", then "[Name] will lose access to DELTA. This cannot be undone." Buttons Cancel and "Delete user" | Names the person being deleted |
| Messages after an action | Added: "User has been successfully added!" Saved: "Changes saved" Deleted: "User deleted successfully." Resent: "Invitation email sent successfully" | Invited: "Invitation sent to [email]." Saved: "Changes saved for [name]." Deleted: "[Name] was deleted." Resent: "Invitation sent again to [email]." | Messages name who was affected |
| Resend invitation | Confirmation dialog "Resend invitation email" | Sent directly from the row, followed by the message above | One step instead of two |
| Organization field | Optional, can be cleared | Optional, no "(required)" marker, choose "No organization" to clear. The list shows "-" when empty | Same rule as today, now stated on the field |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |
| Logo | Placeholder | DELTA Resilience logo, two-line version, 32px high, in the top bar | Brand, kept small |

The columns, the four roles and the add, edit, delete and resend actions exist in both versions.

## Backend

No changes. Organization is already optional in the current invite form, and the Super admin role is not offered in the country role list.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
