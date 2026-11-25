# MSP-003: Account repeatedly locks after a password change

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional user can sign in briefly, then loses access again.

**Area:** Active Directory. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Cached credentials in a task or service; another device retrying; an application using the old password; password spraying.

## Investigation procedure

1. Verify identity and whether the account is locked, disabled or expired. Do not treat these states as interchangeable.
2. Review lockout events on relevant domain controllers and correlate caller details with endpoint logs and the incident timeline.
3. Inspect scheduled tasks, services and saved credentials on the identified source without revealing passwords. Unexpected sources require security triage.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Import-Module ActiveDirectory
Search-ADAccount -LockedOut -UsersOnly
Get-ADUser lab.user -Properties LockedOut,Enabled,PasswordLastSet
Get-WinEvent -ComputerName dc01.lab.example -FilterHashtable @{
    LogName='Security'; Id=4740; StartTime=(Get-Date).AddHours(-2)
} -MaxEvents 30 | Select-Object TimeCreated,Id,Message
```

**Simulated evidence and interpretation:** Fictional timeline: failures recur every five minutes from LAB-WS01 after a password change. A task on that host uses the account. Timing is a lead, not proof.

## Root-cause reasoning

The proposed cause is a scheduled task retaining old credentials. Confirm task execution times against authentication events; a lockout source field may not identify the ultimate origin.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the task owner update its credential configuration or move to an appropriate managed identity. Unlock the account only after identity checks and source correction. Preserve evidence if abuse is suspected.

## Validation and closure criteria

Verify normal sign-in and task execution over several recurrence intervals. Confirm no new lockouts; do not lower the lockout policy.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate unknown sources, privileged accounts or multiple affected users to security. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Search-ADAccount](https://learn.microsoft.com/en-us/powershell/module/activedirectory/search-adaccount)
- [Get-WinEvent](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent)
