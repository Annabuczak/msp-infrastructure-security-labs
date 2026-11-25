# INC-011 | VPN authentication failure

[All scenarios](../README.md#scenario-index)

**Technology:** FortiClient / FortiGate / MFA

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

User cannot authenticate to VPN.

## Investigation

Check profile, account, group membership, authentication logs, MFA, portal and scope.

## Simulated root cause

Account removed from authorised VPN group.

## Proposed resolution

Verify entitlement, restore approved membership and allow synchronisation.

## Verification plan

Confirm VPN, MFA and authorised resource access.

## Skills covered

Identity, VPN, group management

## Diagnostic interpretation and escalation

Check the actual identity source and VPN type before assuming group removal is the cause. Distinguish invalid credentials, MFA failure, SAML/RADIUS issues and a portal or policy mapping problem. Restore membership only after the resource owner confirms entitlement; do not bypass MFA to make the connection work.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
