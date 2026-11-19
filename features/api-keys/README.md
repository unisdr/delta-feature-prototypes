# API keys

Prototype of the API keys screen in DELTA (Settings, API keys). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/api-keys/

## Purpose

Let administrators create and manage the keys other applications use to read and send data.

## Users

- Admins and super admins.

## Scope

- Key list with sorting and pagination.
- Add, edit and delete as dialogs.
- After a key is created, a dialog shows it with a Copy button.

## Not in scope

- Real keys. All keys are examples.

## Changes from the current version

Compared with the current API keys pages in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Add, edit, delete | Each opens as a separate page | Dialogs on the list page | The user keeps their place in the list |
| Errors | Returned by the server after the form is sent | Shown under the field when the button is pressed, cleared when the field is edited | Clear feedback, WCAG 2.2 |
| Confirmations | A message after the page redirects | Short message that fades out | One pattern across screens |
| Sorting | None | Click a column header to sort, click again to reverse, arrow on the sorted column | Find the newest or specific rows |
| Rows per page | 10, 20, 30, 40, 50 | 25, 50, 100, default 25 | Design system standard for tables |
| Key name | Session Secret | Key. The list shows the first 8 characters with a copy button, as today | Plain language |
| Sortable columns | None | Name, managed by, created | Find keys faster |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
