# INC-014 | Incorrect IVR call routing

[All scenarios](../README.md#scenario-index)

**Technology:** Five9 / IVR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Technical support option routes to general enquiries.

## Investigation

Review inbound campaign, published flow, menu destinations, skills, business hours and overflow.

## Simulated root cause

Incorrect menu destination after change.

## Proposed resolution

Obtain approval, preserve rollback configuration, correct destination and test branches.

## Verification plan

Test menu options, hours, overflow and fallback.

## Skills covered

IVR, skill groups, change management

## Diagnostic interpretation and escalation

Confirm the dialled number, inbound campaign and active published flow before editing. Check menu input, target skill, agent eligibility, time zone, holiday rules and overflow. Test each branch and a no-input/invalid-input path in an approved test window. Preserve the previous version and define a rollback trigger.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
