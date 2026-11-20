# Log in

Prototype of the DELTA log in flow: sign in, forgot password and reset password. Built with the DELTA design system (React Aria + Tailwind), version 0.7.2.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/login/

## Purpose

Let people sign in, recover their password and choose an instance.

## Users

- Everyone who has a DELTA account.

## Scope

- Sign in with email and password, and the single sign-on button.
- Forgot your password, Check your email, Enter your code, Select an instance, Loading instance.
- Reset your password and Password changed (the reset link opens from the email).

## Not in scope

- Real sign in, single sign-on and email sending. All of it is example behaviour.
- The code screen is only shown to users with two-step verification turned on. The prototype always shows it so it can be reviewed.

## Changes from the current version

Compared with the current log in screens in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Layout | Single centred card on a grey background | Split screen: beige side with the DELTA text on the left, sign in form on an off-white side on the right. On mobile only the form is shown | Matches the design system layout |
| Screens | Current flow | Same flow, rebuilt from the shared components: Welcome back, Forgot your password, Check your email, Enter your code, Select an instance, Loading instance, Reset your password, Password changed | Consistent with the other screens |
| Logo | DELTA written as text | DELTA Resilience logo, two-line version, 48px high, top left (and above the form on mobile) | Brand, same logo as the top bar on the other pages |
| Instance selection | Dropdown | One list with the Official and Training instances together | Fewer clicks |

The left-hand text is taken from the DELTA landing page.

## Backend

- No changes.

## Assets

- `assets/`: the DELTA Resilience logo (SVG, two-line version).

## Checks

- Automatic accessibility check (axe-core, WCAG 2.0, 2.1 and 2.2 A and AA rules): no problems found.
