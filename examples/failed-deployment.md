# Failed Deployment Example

docs: add failed deployment example case study

## Overview

A true failure scenario illustrating how a deployment went wrong, how it
was detected, and how recovery was executed.\
This file belongs under: `examples/failed-deployment.md`.

## Objectives

-   Demonstrate a realistic failure\
-   Explain what went wrong and why\
-   Teach proper response and recovery patterns\
-   Document resiliency lessons

------------------------------------------------------------------------

## Deployment Context

**Service:** Notification Service\
**Environment:** Production\
**Strategy:** Rolling Update\
**Incident Severity:** SEV‑2\
**Root Cause Category:** Schema incompatibility

------------------------------------------------------------------------

## Scenario Summary

A new schema was introduced in the message producer, but the consumer
service was not updated yet, causing repeated failures and message
backlog.

------------------------------------------------------------------------

## What Went Wrong

-   Producer deployed before consumer\
-   No backward‑compatible schema design\
-   Missing contract tests\
-   Lack of proper queue-based alerting

------------------------------------------------------------------------

## Impact Analysis

-   **Duration:** 6 minutes partial outage\
-   **Users affected:** \~18,000 notifications delayed\
-   **Business impact:** Delayed OTP + signup notifications\
-   **Queue backlog:** 140k messages\
-   **Error spike:** +470%

------------------------------------------------------------------------

## Detection Timeline

  Time    Detection
  ------- ------------------------------------
  14:02   Error rate alarm triggers (Sentry)
  14:03   SQS backlog alarm triggers
  14:04   On‑call engineer paged
  14:05   Crash-loop logs identified
  14:06   Automated rollback started

------------------------------------------------------------------------

## Mitigation & Recovery Process

1.  Rollback triggered automatically\
2.  Last stable consumer version restored\
3.  Queue drained gracefully\
4.  Schema hotfix deployed\
5.  Multi-team post‑mortem meeting conducted

------------------------------------------------------------------------

## Recovery Outcome

-   Full system recovery with no message loss\
-   Normal processing restored after 4 minutes post‑rollback

------------------------------------------------------------------------

## Preventative Measures

-   Add producer/consumer contract tests\
-   Enforce backward compatibility rules\
-   Add real-time queue depth dashboard\
-   Rewrite schema validator with versioning support

------------------------------------------------------------------------

## Teaches

**Error detection, quick incident response, rollback discipline, and
recovery operations.**
