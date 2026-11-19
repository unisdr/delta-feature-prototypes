# System settings

Prototype of the System settings screen in DELTA (Settings, System settings). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/system-settings/

## Purpose

Show how this instance of DELTA is set up and let administrators edit the instance name and language.

## Users

- Super admins and admins.

## Scope

- Settings in four groups: Instance, Country, Email, Software. Each group says who can change it.
- One Edit dialog for instance name and language.

## Not in scope

- Saving real settings. Values are example data.

## Changes from the current version

Compared with the current System settings page in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Grouping | Country instance, Instance configuration, Software, Email routing | Four groups: Instance, Country, Email, Software, each saying who can change it | Easier to scan, and it says who to ask |
| Authenticator name | 2FA/TOTP Issuer Name | Name shown in authenticator apps | Plain language |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
