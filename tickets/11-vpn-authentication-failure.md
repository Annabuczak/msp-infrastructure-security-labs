# INC-011 | VPN authentication failure

[All tickets](../README.md#ticket-index)

**Technology:** FortiClient / FortiGate / MFA

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

User cannot authenticate to VPN.

## Investigation

Check profile, account, group membership, authentication logs, MFA, portal and scope.

## Root cause assessment

Account removed from authorised VPN group.

## Response procedure

Verify entitlement, restore approved membership and allow synchronisation.

## Verification checks

Confirm VPN, MFA and authorised resource access.

## Skills covered

Identity, VPN, group management

## Additional diagnostic guidance

Check the actual identity source and VPN type before assuming group removal is the cause. Distinguish invalid credentials, MFA failure, SAML/RADIUS issues and a portal or policy mapping problem. Restore membership only after the resource owner confirms entitlement; do not bypass MFA to make the connection work.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
