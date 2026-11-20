# Organization management

Prototype of the Organization management screen in DELTA (Settings, Organization management). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/organization-management/

## Purpose

Let administrators add, edit and delete the organizations people belong to.

## Users

- Admins and super admins.

## Scope

- Organization list with search, sorting and pagination.
- Add, edit and delete organizations as dialogs.
- A Users column with the number of users per organization.

## Not in scope

- Real data. Organizations are example data.

## Changes from the current version

Compared with the current Organization management page in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Add, edit, delete | Each opens as a separate page | Dialogs on the list page | The user keeps their place in the list |
| Errors | Returned by the server after the form is sent | Shown under the field when the button is pressed, cleared when the field is edited | Clear feedback, WCAG 2.2 |
| Confirmations | A message after the page redirects | Short message that fades out | One pattern across screens |
| Sorting | None | Click a column header to sort, click again to reverse, arrow on the sorted column | Find the newest or specific rows |
| Rows per page | 10, 20, 30, 40, 50 | 25, 50, 100, default 25 | Design system standard for tables |
| Users column | Not shown (the list has a Name column only) | Number of users in each organization | Admins can see which organizations are in use |
| Delete when users remain | Error appears after trying | The dialog says up front that the organization still has users and what to do | Avoids a failed action |
| Sortable columns | None | Name and users | Find organizations faster |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- The list includes the number of users per organization.
- 25 rows per page by default, with 50 and 100 as the other choices.
- Sorting applies to the whole list, not only the rows on the current page.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
