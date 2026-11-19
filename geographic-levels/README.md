# Geographic levels

Prototype of the Geographic levels screen in DELTA (Settings, Geographic levels). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/geographic-levels/

## Purpose

Let administrators manage the administrative divisions of the country, used to say where an event happened.

## Users

- Admins and super admins.

## Scope

- One tree with level, national ID and boundary status for each division.
- Search, expand all and collapse all.
- Add a division inside another, edit and delete.
- Upload ZIP as a dialog, with a list of failed rows after upload.
- Edit dialog with the boundary on a map.

## Not in scope

- Real boundaries. The outline on the map is a placeholder drawing.

## Changes from the current version

Compared with the current Geographic levels pages in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Views | Tree view and Table view tabs, with search and Expand all in the tree view | One tree with search, Expand all and Collapse all. Each row shows the level, national ID and whether a boundary file is uploaded, with buttons to add inside, edit and delete | One view instead of two |
| Parent | Type a parent ID | Pick the parent from a list (Belongs to) | No need to know IDs |
| Names | One column per language | Shown in the interface language. The dialog has one name field per language | Multi-language support |
| Boundary | Separate view page | Shown on a map in the edit dialog | Fewer pages |
| Upload ZIP | Separate upload page | Dialog. After the upload it lists the rows that failed and why | The user can fix the file |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- The list says for each division whether a boundary is set.
- A boundary can be replaced with a new file. Today a file can only be uploaded when the division has none.
- For countries with many divisions, the divisions inside a row are loaded when the row is opened.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
