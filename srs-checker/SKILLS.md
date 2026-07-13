---
name: srs-checker
description: Check SRS files match the spec
license: MIT
metadata:
  author: Reggie Bigornia
  version: 0.1.0
---

Going forward, any mention of srs refers to software requirements specification

## What I do

- Compare a given file to the srs spec
- List issues if they exist
- Any formatting issues in the list must not be updated without user confirmation

## When to use me

Use this when you are asked to check if an srs document is correct.

The ff phrases can be used to trigger this skill:
- `check this srs`
- `srs check`
- `run srs-checker on this document`
- `check srs`
- `srs-checker`
- `srs checker`

If you are unsure of what document to run this skill against, ALWAYS ask for clarification.

## The srs template

The following is the template that you will base your check on

```
# Project: {{project-name}} MVP

## I. The Domain & Vision

This section will answer 2 questions
1. What does this project do?
2. What doesn't this project do?

It is important that this section answers the question of what this project doesn't do. This information will prevent scope creep and keep the project on schedule.

This section will be formatted as sentences or paragraphs.

## II. Actors & Core Entities

This section describes the project's actors and entities

### Actors:

The list of actors will go here

### Entities:

The list of entities will go here

## III. MVP User Stories

This section will be a checklist of user stories in the ff format:

As a/an {{actor}}, I want to {{action}}
or
As a/an {{actor}}, I want to {{action}} so that {{reason}}

Note that the reason is optional and the presence of a reason for each checklist item will guide you on which format to use

The stories in this list will define the scope boundary of the project and will be used as a basis for the tasks that should be done. It is possible that some user stories can be broken down into multiple tasks. Any tasks that do not fit into any of the user stories above should not be included in this MVP.

## IV. Non-Functional Constraints

This section will be a list of constraints for the project that are non-functional. This means that the list will describe how the project behaves rather than what it does.

The format for each list item should be a single sentence.
```

## Example srs

The following is an example srs for a todo app

```
# Project: Lean Task Tracker (MVP)

## I. The Domain & Vision

A minimalist, lightning-fast personal To-Do app focused on daily execution.

This project will not include features for Team sharing, sub-tasks, calendar integrations, and recurring tasks.

## II. Actors & Core Entities

### Actors:

 - Standard User (authenticated)
 - Guest User (unauthenticated)

### Entities:

- `User`
  - email
  - password
  - creation date
- `Task`
  - title
  - status
  - created date
  - due date
  - tag ID
- `Tag`
  - name
  - color code

## III. MVP User Stories

- [ ] As a Guest, I want to try the app without signing up so I can see if I like it.
- [ ] As a User, I want to quickly type a task and hit Enter to save it.
- [ ] As a User, I want to toggle a checkbox to mark a task as complete.
- [ ] As a User, I want to filter my list by Tags to focus on specific contexts (e.g., "Work", "Home").

## IV. Non-Functional Constraints
- **Performance:** Total page weight under 500kb; tasks must render instantly.
- **Security:** JWT-based session management; bcrypt password hashing.
```

