# Sectors

Prototype of the Sectors screen in DELTA (Settings, Sectors). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/sectors/

## Purpose

Show the sectors used to classify losses and damages. The list is read-only.

## Users

- Admins and super admins.

## Scope

- One read-only tree with level and description beside each name.
- Search, expand all and collapse all.

## Not in scope

- Editing sectors. The list is the same for every country.
- The sector names are sample content.

## Changes from the current version

Compared with the current Sectors pages in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Views | Tree view and Table view tabs | One read-only tree, with the level and description beside each name, search, Expand all and Collapse all | One view instead of two |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
