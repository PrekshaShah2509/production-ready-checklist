# Lessons Learned Example

docs: add lessons learned documentation example

## Overview

A structured example of how to document learnings from incidents to
drive organization-wide improvement.\
This file belongs under: `examples/lessons-learned.md`.

## Objectives

-   Provide a reusable structure for post‑incident learning\
-   Capture root causes clearly\
-   Define measurable prevention steps\
-   Assign ownership to ensure follow‑through

------------------------------------------------------------------------

## Timeline of Events

  Time    Description
  ------- ------------------------
  09:20   Deployment initiated
  09:22   Issue observed in logs
  09:25   Team notified
  09:27   Rollback initiated
  09:30   Service restored
  10:00   Post‑incident sync

------------------------------------------------------------------------

## Root Cause Analysis (5 Whys)

1.  **Why?** Consumer crashed due to invalid schema\
2.  **Why?** Schema changed without consumer support\
3.  **Why?** Deployment order reversed\
4.  **Why?** No dependency validation in CI\
5.  **Why?** Missing cross‑service integration tests\
    **→ True Root Cause: Lack of enforced inter‑service contract
    testing**

------------------------------------------------------------------------

## What Went Well

-   Fast detection\
-   Effective rollback automation\
-   Strong team communication

------------------------------------------------------------------------

## What Went Wrong

-   Missing schema validation\
-   No producer--consumer contract tests\
-   Alerts not tuned for early detection

------------------------------------------------------------------------

## Future Prevention Measures

-   Introduce schema versioning\
-   Mandate contract testing in CI\
-   Strengthen rollback procedure templates\
-   Improve communication between platform and backend teams

------------------------------------------------------------------------

## Action Items & Ownership

  Action Item                      Owner          Priority   Status
  -------------------------------- -------------- ---------- -------------
  Add schema validation tests      Backend Lead   High       Pending
  Add queue-depth dashboard        DevOps         Medium     In Progress
  Update deployment playbook       Eng. Manager   High       Pending
  Add integration contract tests   QA Lead        High       Pending

------------------------------------------------------------------------

## Teaches

**Organizational learning through process, tooling, and communication
improvements.**
