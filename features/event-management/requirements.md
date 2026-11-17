# Event Management — Requirements

## 1. Overview
This document captures the implementation-ready functional requirements for the Event Management feature. It supplements the prototype and is intended to be the source of truth for business rules, calculations, validation logic, and acceptance criteria during development.

## 2. Purpose
The feature supports teams in reviewing, tracking, and acting on events across their lifecycle. It provides a single operational view of event status, ownership, and key details needed for decision-making.

## 3. User roles
- Event manager
- Team lead
- Viewer
- Administrator

## 4. Scope
In scope:
- viewing event summaries
- filtering and scanning event records
- reviewing selected event detail
- identifying event status and ownership
- supporting action-oriented operational review

Out of scope:
- full production workflow automation
- advanced reporting beyond the prototype scope
- external system integration design

## 5. Inputs
- event name
- event status
- event owner
- event date
- region or location
- event type
- registration or participation count
- notes or operational comments

## 6. Outputs
- event summary metrics
- event list
- event detail panel
- validation messages
- status indicators
- action states for selected event

## 7. Business rules

### BR-01: Event status visibility
The system must show a visible event status for each event record.
- Trigger: record is displayed in the event list
- Condition: status is known
- Result: status label is shown in the UI

### BR-02: Draft events require review
An event in draft status must be clearly identifiable as requiring follow-up action.
- Trigger: event is saved with status = draft
- Result: event is flagged for review and remains visible in the active queue

### BR-03: Archived events are excluded from default active workflow
Archived events should not be included in normal operational review unless the user explicitly chooses to view archived records.
- Trigger: default event dashboard load
- Condition: event status = archived
- Result: archived items are excluded from the default list view

### BR-04: Event ownership is required for active records
An active event must have an assigned owner.
- Trigger: record is submitted or saved
- Condition: owner is empty for active, draft, or review states
- Result: save is blocked and a validation error is shown

### BR-05: Duplicate event names are flagged
The system must prevent duplicate active event names within the same scope when a matching record already exists.
- Trigger: save or submission event
- Condition: same event name exists in the same operational scope
- Result: save is blocked and user is notified of the duplicate

## 8. Calculations and formulas

### CALC-01: Active event count
Formula: active_event_count = count(events where status is active, draft, or review)

### CALC-02: Upcoming events count
Formula: upcoming_event_count = count(events where event_date >= today and status is not archived)

### CALC-03: Total registrations
Formula: total_registrations = SUM(registration_count for all active events in current scope)

### CALC-04: Status summary values
Summary metrics should reflect only records that match the relevant status filter and exclude archived items unless archived view is selected.

### Rounding and precision
- numeric summary values should be displayed as whole numbers unless a decimal result is explicitly required
- calculation totals should be rounded to 2 decimal places when fractional values are involved

## 9. Validation rules
- If event name is empty, the record cannot be saved.
- If owner is empty for an active record, the record cannot be saved.
- If event date is missing, the record cannot be saved.
- If a duplicate event name is detected in the same scope, saving is prevented.
- If a status is archived, the record must be excluded from default active filters.

## 10. Edge cases
- no events match the current filter
- archived records are selected for review
- duplicate names across different regions
- future-dated events included in upcoming count
- missing owner information on draft items
- null or incomplete registration counts

## 11. Acceptance criteria
- AC-01: The event dashboard shows summary metrics based on the current active dataset.
- AC-02: Active, draft, and review items are visible in the default operational list.
- AC-03: Archived events are hidden from default active views unless a user selects archived mode.
- AC-04: Events without assigned owners are blocked from save in active states.
- AC-05: Duplicate names within the same scope trigger a validation message.
- AC-06: Summary counts update when the user changes filters or status selection.
- AC-07: User actions are shown in context with the selected event record.

## 12. Implementation note
This document should be treated as the implementation specification. The prototype in `index.html` demonstrates interaction and layout only; business rules and calculations must be enforced in the application logic and validated against this specification.
