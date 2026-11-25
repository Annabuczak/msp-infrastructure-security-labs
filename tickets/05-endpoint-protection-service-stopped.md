# INC-005 | Endpoint protection service stopped

[All tickets](../README.md#ticket-index)

**Technology:** Sophos Central

**Priority:** P2 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Pending restart after update.

## Response procedure

Arrange authorised restart; escalate persistent failures.

## Verification checks

Confirm healthy protection and update services.

## Skills covered

Endpoint health, patching, Windows services

## Additional diagnostic guidance

A restart requirement is a hypothesis until correlated with update logs and the service failure time. Check whether the stopped service is expected to run continuously in this installed version. Confirm fresh Central check-in and active protection after the authorised restart; a running Windows service alone is insufficient.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
