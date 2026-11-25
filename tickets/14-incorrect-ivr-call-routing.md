# INC-014 | Incorrect IVR call routing

[All tickets](../README.md#ticket-index)

**Technology:** Five9 / IVR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

Technical support option routes to general enquiries.

## Investigation

Review inbound campaign, published flow, menu destinations, skills, business hours and overflow.

## Root cause assessment

Incorrect menu destination after change.

## Response procedure

Obtain approval, preserve rollback configuration, correct destination and test branches.

## Verification checks

Test menu options, hours, overflow and fallback.

## Skills covered

IVR, skill groups, change management

## Additional diagnostic guidance

Confirm the dialled number, inbound campaign and active published flow before editing. Check menu input, target skill, agent eligibility, time zone, holiday rules and overflow. Test each branch and a no-input/invalid-input path in an approved test window. Preserve the previous version and define a rollback trigger.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
