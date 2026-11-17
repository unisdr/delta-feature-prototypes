# Access management

Prototype of the Access management screen in DELTA (Settings, Access management). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/access-management/

## Purpose

Let administrators invite people to a site and set what they can do on it.

## Users

- Admins and super admins who manage access for one site.

## Scope

- User list with search by name, email or organization and a role filter.
- Sorting on name, status, organization, role and date added. Sorting applies to the whole list.
- Pagination: 25, 50 or 100 rows per page, default 25.
- Invite user, edit user and delete user as dialogs on the list page.
- Resend invitation for users whose invitation is pending.

## Not in scope

- Real data and sign-in. All users and organizations are example data.
- Permissions per feature beyond the five roles.

## Checks

- axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules: no violations.
