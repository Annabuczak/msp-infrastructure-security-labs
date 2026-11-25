# INC-018 | Suspicious Entra sign-in

[All scenarios](../README.md#scenario-index)

**Technology:** Entra ID / MFA

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Unrecognised successful sign-in.

## Investigation

Review interactive/non-interactive logs, IP/location, device, app, MFA, CA and related activity; contact user via trusted channel.

## Simulated root cause

User denies sign-in; potential compromise.

## Proposed resolution

Escalate, block access where authorised, revoke sessions, reset credentials, review authentication methods, mailbox rules and app consent.

## Verification plan

Restore only after clearance and monitor further activity.

## Skills covered

Identity threat triage, containment

## Diagnostic interpretation and escalation

An unfamiliar IP or location is a signal, not a confirmed compromise mechanism. Correlate user confirmation, device, app, authentication details and subsequent actions. Preserve logs and escalate under the identity incident process. Session revocation is not guaranteed to terminate every existing application session immediately; check application behaviour and monitor after containment.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
