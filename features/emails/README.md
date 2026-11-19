# Emails

The six DELTA emails on one shared layout. Built to the DELTA design system, version 0.7.2, with the tokens written as fixed values because email apps do not support design tokens.

Live preview: https://unisdr.github.io/delta-feature-prototypes/features/emails/

## Purpose

Give every email DELTA sends the same look: logo, content, one button and a footer.

## Users

- Everyone who receives an email from DELTA.

## Scope

- Invitation, invitation for an existing user, welcome, reset password, password changed and confirm new email address.
- `index.html` shows all six in one page. `templates/` has the six email files.

## Not in scope

- Sending. The templates use `{logoURL}` and other placeholders that DELTA fills in.
- The plain text versions of the emails. They stay as they are today.

## Changes from the current version

Compared with the current emails in DELTA.

| Area | Current | Prototype | Reason |
|---|---|---|---|
| Layout | Each email is its own HTML string in the code | One shared layout: the DELTA Resilience logo top left, content, button, footer with the UNDRR name. Each email fills in the content only | One look across all emails |
| Logo | No logo in the emails | PNG file hosted on the DELTA site. If the inbox blocks images, the text "DELTA Resilience" shows in its place | Emails cannot link to a file inside the app |
| Button | Hardcoded blue button | One button style, with the plain link under it | The user can copy the link if the button does not work |
| Build | Written as plain HTML strings in the code | Tables and inline styles, so the emails look the same in Outlook, Gmail and phone apps | Email apps support little CSS |
| Copy | Current wording | Shortened. Headlines: Invitation "Set up your account", invitation for an existing user "You have a new instance". Reset password and Password changed keep their headlines with a new first sentence | Headline and first sentence do not repeat |

The "external sender" banner some inboxes show is added by the UN mail system, not by DELTA.

## Backend

- Confirm new email address is a new email. It is sent to the new address when an administrator changes a user's email, and the change only applies once the user confirms. This needs a pending email address, a confirmation link and a route to confirm it.
- No changes to the other five emails.

## Assets

- `assets/delta-resilience-logo.png`: the logo used at the top of every email (562 x 156 px, shown at 158 x 44 px). It must be hosted on the DELTA site and its address passed to the templates as `{logoURL}`.

## Checks

- Not run in a browser accessibility check. Emails need testing in real inboxes (Outlook, Gmail, a phone app).
