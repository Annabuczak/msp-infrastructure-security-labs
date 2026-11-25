# INC-005 | Endpoint protection service stopped

[All scenarios](../README.md#scenario-index)

**Technology:** Sophos Central

**Priority:** P2 · **Support level:** Tier 1

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Endpoint health alert.

## Investigation

Check services, recent updates, restart requirements and system events.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Get-Service *Sophos*
Get-WinEvent -LogName System -MaxEvents 50
```

## Simulated root cause

Pending restart after update.

## Proposed resolution

Arrange authorised restart; escalate persistent failures.

## Verification plan

Confirm healthy protection and update services.

## Skills covered

Endpoint health, patching, Windows services

## Diagnostic interpretation and escalation

A restart requirement is a hypothesis until correlated with update logs and the service failure time. Check whether the stopped service is expected to run continuously in this installed version. Confirm fresh Central check-in and active protection after the authorised restart; a running Windows service alone is insufficient.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
