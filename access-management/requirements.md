# Access management - requirements

Status: prototype. Version of the design system: 0.7.2.

## Purpose

Let admins invite people to a site, set their role and remove their access.

## Users

- Admins of one site.

## Roles

| Role | Can |
|---|---|
| Data viewer | View data and use analytics |
| Data collector | Add, edit and import data |
| Data validator | Validate data |
| Admin | Manage access and country settings |

Super admin is a global role and is not set from a site.

## Fields

| Field | Required | Rules |
|---|---|---|
| Email | Yes | Valid email address. Read-only when editing a user |
| Organization | No | Chosen from the site's organizations. "No organization" clears it. The list shows "-" when empty |
| Role | Yes | One of the four roles. The text under the field says what the role can do |

## Business rules

1. Errors are shown under the field when the user presses the button, and cleared when the field is edited.
2. Required fields carry "(required)" in the label. Optional fields carry no marker.
3. A user with a pending invitation can be sent the invitation again from the row.
4. Deleting a user removes their access. The dialog names the user and says it cannot be undone.
5. General rule for all dialogs: clicking outside the dialog does not close it, so no one loses what they typed. A dialog closes only with its Cancel button, its close button or the Escape key.
6. After each action a short message names who was affected.

## List

- One search box (name, email, organization) and a role filter.
- Sorting on name, status, organization, role and date added. It applies to the whole list.
- Pagination: 25, 50 or 100 rows per page, default 25.

## Backend

The prototype needs two changes on the server. Everything else is front end only.

- Search: today the list reads one organization filter and one role filter. The new search box looks in name, email and organization, so the list query needs a search term.
- Sorting: today the list is paginated on the server and has no order. Sorting applies to the whole list, so the query needs a sort column and direction.

Not backend: rows per page (25, 50, 100), dialogs, messages, labels. Organization is already optional in the current invite form, and the Super admin role is not offered in the country role list.

## Open questions

- Should an admin be able to change their own role?
- Should deleting a user with records need a transfer of ownership first?
- Should the user count ("Currently there are N users") stay?
