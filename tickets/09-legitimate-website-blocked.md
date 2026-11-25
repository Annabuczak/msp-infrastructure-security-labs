# INC-009 | Legitimate website blocked

[All tickets](../README.md#ticket-index)

**Technology:** FortiGuard

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

## Incident description

Approved business site blocked.

## Investigation

Collect URL and block page; check scope, web filtering logs, category and applicable policy.

## Root cause assessment

Site categorised as restricted.

## Response procedure

Validate site, request reassessment or approved narrow exception.

## Verification checks

Confirm approved site accessible; unrelated restrictions remain.

## Skills covered

Web filtering, firewall logs

## Additional diagnostic guidance

Determine whether the denial comes from web category policy, a static URL filter, DNS filtering or certificate inspection. Business approval does not establish that a site is safe. Record the exact category and matching policy; prefer reassessment or a narrowly scoped, reviewed exception over a category-wide bypass.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
