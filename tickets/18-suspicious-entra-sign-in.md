# INC-018 | Suspicious Entra sign-in

[All tickets](../README.md#ticket-index)

**Technology:** Entra ID / MFA

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

Unrecognised successful sign-in.

## Investigation

Review interactive/non-interactive logs, IP/location, device, app, MFA, CA and related activity; contact user via trusted channel.

## Root cause assessment

User denies sign-in; potential compromise.

## Response procedure

Escalate, block access where authorised, revoke sessions, reset credentials, review authentication methods, mailbox rules and app consent.

## Verification checks

Restore only after clearance and monitor further activity.

## Skills covered

Identity threat triage, containment

## Additional diagnostic guidance

An unfamiliar IP or location is a signal, not a confirmed compromise mechanism. Correlate user confirmation, device, app, authentication details and subsequent actions. Preserve logs and escalate under the identity incident process. Session revocation is not guaranteed to terminate every existing application session immediately; check application behaviour and monitor after containment.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
