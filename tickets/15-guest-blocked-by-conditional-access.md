# INC-015 | Guest blocked by Conditional Access

[All scenarios](../README.md#scenario-index)

**Technology:** Entra ID / Teams

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

External guest cannot access shared resource after invitation.

## Investigation

Check account, redemption, sign-in logs, CA results, compliance, MFA, cross-tenant settings and resource permissions.

## Simulated root cause

Guest cannot satisfy compliant device requirement.

## Proposed resolution

Review cross-tenant trust or narrowly scoped guest policy with security administrator; retain necessary MFA and protections.

## Verification plan

Verify only authorised resource access.

## Skills covered

B2B, Conditional Access, least privilege

## Diagnostic interpretation and escalation

Use the failed sign-in policy results to identify the control that actually blocked access. Cross-tenant trust accepts specified claims from a trusted tenant; it does not grant resource permission. Evaluate guest scope and trust with the security administrator rather than excluding all guests from Conditional Access.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
