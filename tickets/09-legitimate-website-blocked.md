# INC-009 | Legitimate website blocked

[All scenarios](../README.md#scenario-index)

**Technology:** FortiGuard

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Approved business site blocked.

## Investigation

Collect URL and block page; check scope, web filtering logs, category and applicable policy.

## Simulated root cause

Site categorised as restricted.

## Proposed resolution

Validate site, request reassessment or approved narrow exception.

## Verification plan

Confirm approved site accessible; unrelated restrictions remain.

## Skills covered

Web filtering, firewall logs

## Diagnostic interpretation and escalation

Determine whether the denial comes from web category policy, a static URL filter, DNS filtering or certificate inspection. Business approval does not establish that a site is safe. Record the exact category and matching policy; prefer reassessment or a narrowly scoped, reviewed exception over a category-wide bypass.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
