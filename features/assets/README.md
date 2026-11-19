# Assets

Prototype of the Assets screen in DELTA (Settings, Assets). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/assets/

## Purpose

Let administrators see the types of asset that can be recorded as damaged or destroyed, and manage custom ones.

## Users

- Admins and super admins.

## Scope

- Asset list with search, type filter, sorting and pagination.
- View for built-in assets. Edit and delete for custom assets.
- Import CSV, Export CSV and Add asset.

## Not in scope

- Real data. Assets are example data.

## Changes from the current version

Compared with the current Assets pages in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Add, edit, delete | Each opens as a separate page | Dialogs on the list page | The user keeps their place in the list |
| Errors | Returned by the server after the form is sent | Shown under the field when the button is pressed, cleared when the field is edited | Clear feedback, WCAG 2.2 |
| Confirmations | A message after the page redirects | Short message that fades out | One pattern across screens |
| Sorting | None | Click a column header to sort, click again to reverse, arrow on the sorted column | Find the newest or specific rows |
| Rows per page | 10, 25, 50 | 25, 50, 100, default 25 | Design system standard for tables |
| Actions | Actions column | Built-in assets have a View button only. Custom assets have Edit and Delete | Built-in assets cannot be changed |
| Category | Not shown (columns are Name, Sector(s), Is custom, Actions) | New Category column | Helps find assets |
| Type | Is custom | Type column with Built-in or Custom | Plain language |
| Sortable columns | None | Name, category, type | Find assets faster |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
