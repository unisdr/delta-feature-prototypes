# Profile

Prototype of the Profile screen in DELTA (account menu, Profile). Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/profile/

## Purpose

Let people see their details and manage how they sign in.

## Users

- Every signed in user.

## Scope

- Your details: name, email, organization, role.
- Sign in and security: password and two-step verification.
- Edit name, change password, turn on and turn off two-step verification as dialogs.

## Not in scope

- Real password and two-step verification checks. The QR code and setup key are examples.

## Changes from the current version

Compared with the current profile, change password and TOTP pages in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Pages | Separate profile, change password, enable TOTP and disable TOTP pages | One profile page with two groups: Your details, and Sign in and security | One place for everything about the account |
| Edit name, password, two-step verification | Separate pages | Dialogs on the profile page | The user keeps their place |
| Account menu | Profile, Change password, TOTP (2FA) and Sign out, each opening its own page | Profile and Sign out only. Change password and two-step verification are on the profile page | One page for the account, so the menu does not repeat it. No backend change |
| Two-step verification name | 2FA (TOTP), Enabled and Disabled | Two-step verification, On and Off | Plain language |
| Errors and confirmations | Returned by the server after the form is sent | Errors after the button is pressed and cleared when the field is edited. Confirmations fade out | Same pattern as the other screens |
| Closing dialogs | Clicking outside the dialog does not close it (the code does not turn that on; PrimeReact default) | Same. A dialog closes only with Cancel, the close button or Escape | Now a design system rule (DESIGN.md, Dialog dismiss), so nobody loses what they typed |

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo used in the top bar (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
