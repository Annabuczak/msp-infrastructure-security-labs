# INC-015 | Guest blocked by Conditional Access

[All tickets](../README.md#ticket-index)

**Technology:** Entra ID / Teams

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

External guest cannot access shared resource after invitation.

## Investigation

Check account, redemption, sign-in logs, CA results, compliance, MFA, cross-tenant settings and resource permissions.

## Root cause assessment

Guest cannot satisfy compliant device requirement.

## Response procedure

Review cross-tenant trust or narrowly scoped guest policy with security administrator; retain necessary MFA and protections.

## Verification checks

Verify only authorised resource access.

## Skills covered

B2B, Conditional Access, least privilege

## Additional diagnostic guidance

Use the failed sign-in policy results to identify the control that actually blocked access. Cross-tenant trust accepts specified claims from a trusted tenant; it does not grant resource permission. Evaluate guest scope and trust with the security administrator rather than excluding all guests from Conditional Access.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
