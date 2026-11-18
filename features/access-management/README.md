# Access management

Prototype of the Access management screen in DELTA (Settings, Access management). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/access-management/

## Purpose

Let administrators invite people to a site and set what they can do on it.

## Users

- Admins and super admins who manage access for one site.

## Scope

- User list with search and a role filter.
- Sorting on name, status, organization, role and date added. Sorting applies to the whole list.
- Pagination with a rows per page choice.
- Invite user, edit user and delete user as dialogs on the list page.
- Resend invitation for users whose invitation is pending.

## Not in scope

- Real data and sign-in. All users and organizations are example data.
- Permissions per feature beyond the five roles.

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

The columns, the five roles, resend invitation and the add, edit and delete actions are the same as in the current version.

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
