# DELTA Feature Prototypes

This repository hosts static UI prototypes for the DELTA Design System, aligned to the principles and design language developed in the main project:

- DELTA Design System: https://github.com/unisdr/delta-design

The purpose of this repository is to test and review feature-level concepts in a lightweight, shareable format that can be previewed directly through GitHub Pages.

## Live preview

The project is published at:

- https://unisdr.github.io/delta-feature-prototypes/

Each feature prototype is served from its feature directory using `index.html` as the entry page.

Expected pattern:

- https://unisdr.github.io/delta-feature-prototypes/features/[feature-name]/

Example:

- https://unisdr.github.io/delta-feature-prototypes/features/event-management/

## Repository structure

```text
├── README.md
├── features/
│   ├── event-management/
│   │   ├── README.md
│   │   ├── index.html
│   │   └── notes.md
│   ├── geographic-divisions/
│   ├── data-import/
│   └── user-management/
```

## Principles

This repository follows the DELTA design system approach by keeping prototypes:

- user-focused
- modular and reusable
- aligned to clear information hierarchy
- accessible and readable
- structured for design review and iteration

## File conventions

Each feature folder can include:

- `index.html` — the main prototype entry page for GitHub Pages access
- `README.md` — feature purpose, scope, and user context
- `requirements.md` — implementation-ready functional requirements, business rules, calculations, validation logic, and acceptance criteria
- `notes.md` — design decisions, interaction decisions, rationale, and open questions

`requirements.md` should be treated as the handoff artifact for development. It is the source of truth for business rules and computation logic, while `index.html` remains a design prototype and `notes.md` remains a design rationale document.

### Recommended content for `notes.md`

`notes.md` should primarily capture design and interaction decisions rather than free-form implementation notes. Recommended sections include:

- design decisions
- interaction decisions
- rationale
- alternatives considered
- open questions
- unresolved requirements

This keeps the file useful for both human reviewers and AI-assisted analysis.

A structured example is recommended:

```md
---
feature: event-management
status: prototype
owner: design-review
---

## Design decisions
- Use a three-panel layout for overview, list, and detail

## Interaction decisions
- Selecting an event updates the details panel without page reload
- Status changes are confirmed with inline feedback

## Rationale
- Supports quick scanning of active events while preserving detail

## Open questions
- Should archived events be visible by default?
```

This approach makes the document easier to read, easier to review, and easier for AI tools to summarize or extract structured insights from.

## Example feature

A sample feature has been included to test the repository structure and preview flow:

- `features/event-management/`

This example follows the DELTA design principles and demonstrates a simple event-management prototype with a working GitHub Pages entry point.

Reference sample from the DELTA design project:

- https://unisdr.github.io/delta-design/delta-react-aria-example.html

## Creating a new feature

To add a new prototype:

1. Create a new directory under `features/`.
2. Add an `index.html` page for the prototype.
3. Add a `README.md` with problem statement, user need, and scope.
4. Add a `requirements.md` with functional requirements, business rules, calculations, validation logic, and acceptance criteria.
5. Add `notes.md` with decisions, rationale, and open questions.
6. Keep asset links relative so the page renders correctly on GitHub Pages.

Example structure:

```text
features/
  alert-management/
    README.md
    requirements.md
    index.html
    notes.md
```

## Notes

This repository is intended for design exploration, prototype review, and collaborative iteration. It supplements the main application work and is optimized for static, browser-based previewing.
