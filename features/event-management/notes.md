---
feature: event-management
status: prototype
inspiration: https://unisdr.github.io/delta-design/delta-react-aria-example.html
---

## Design decisions

- Use a top summary bar to expose key metrics before users inspect the event list.
- Place the event list in the main content panel to support fast scanning and triage.
- Use a right-hand detail panel to keep event context visible without leaving the dashboard.

## Interaction decisions

- Selecting a row in the event table updates the detail panel without a page reload.
- Status pills communicate event health using high-contrast color and labels.
- Action buttons remain close to the selected event context to reduce unnecessary navigation.

## Rationale

This structure reduces cognitive load by separating overview, list, and detail into clear zones. It keeps the page understandable at a glance while still allowing action-oriented workflows.

## Alternatives considered

- A single-column list-only layout, which would reduce visual hierarchy.
- A full-page detail view for every item, which would create more navigation friction.

## Open questions

- Should archived events be grouped separately or hidden by default?
- Are there additional filters required for event type, region, or status?
- Should event creation be a modal flow or a dedicated page?
