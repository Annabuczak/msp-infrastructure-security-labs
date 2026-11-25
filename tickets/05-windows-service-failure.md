# MSP-005: Business application service will not start

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional application is unavailable after maintenance.

**Area:** Windows services. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Invalid service credentials; dependency failure; configuration error; port conflict; insufficient disk space.

## Investigation procedure

1. Record the service name, startup mode, recent changes and exact error. Check dependencies and available storage before restarting repeatedly.
2. Correlate Service Control Manager events with application logs. Inspect the configured service identity without exposing credentials.
3. For a logon error, check credential rotation, account state and log-on-as-a-service policy with the service owner.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-Service -Name LabAppSvc -RequiredServices
Get-CimInstance Win32_Service -Filter "Name='LabAppSvc'" |
    Select-Object Name,State,StartMode,StartName
Get-WinEvent -FilterHashtable @{
    LogName='System'; ProviderName='Service Control Manager'
    StartTime=(Get-Date).AddHours(-2)
} -MaxEvents 30 | Select-Object TimeCreated,Id,Message
```

**Simulated evidence and interpretation:** Invented event summary: service logon failed immediately after service-account rotation. No actual event was collected.

## Root-cause reasoning

The exercise proposes a credential configuration mismatch. A service stopped state alone does not identify a cause.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

The application owner corrects the service identity configuration and starts the service in an agreed window. Retain the prior configuration; never roll back to an exposed password.

## Validation and closure criteria

Check service stability, application health and dependent jobs. Verify recovery after a planned restart if in scope.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate repeated crashes, data corruption or security-related account changes. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Get-WinEvent](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent)
