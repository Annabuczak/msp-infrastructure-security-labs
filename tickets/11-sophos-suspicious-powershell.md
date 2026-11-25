# MSP-011: Suspicious PowerShell alert requires triage

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional endpoint raises an alert for unusual PowerShell execution.

**Area:** Sophos XDR and response. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Approved administration; a software installer; malicious execution; incomplete telemetry causing a misleading chain.

## Investigation procedure

1. Preserve alert ID, UTC time, host identity, user, command line and available process ancestry. Compare with change records; obfuscation is a signal, not a verdict.
2. Review available threat graph and related file/network events. Correlate local event logs where collection is enabled; absence of logs is not proof of absence.
3. Escalate credible malicious behaviour promptly. An authorised responder decides containment while preserving volatile evidence and business context.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-WinEvent -FilterHashtable @{
    LogName='Microsoft-Windows-PowerShell/Operational'
    Id=4104; StartTime=(Get-Date).AddHours(-2)
} -MaxEvents 50 | Select-Object TimeCreated,Id,Message
```

**Simulated evidence and interpretation:** Fictional chain: document reader → PowerShell → outbound connection. A matching maintenance record is absent. No malicious payload or genuine event log is included.

## Root-cause reasoning

The exercise remains a suspected incident. A process chain alone cannot establish entry point, full scope or attacker intent.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Preserve findings and request authorised containment if warranted. Search related hosts and account activity; do not run an unknown command to reproduce it. Recovery follows incident-lead approval, not merely alert closure.

## Validation and closure criteria

Check containment state, investigation scope and telemetry continuity. Define an observation period and recovery criteria with the incident lead.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate suspicious execution plus persistence, credential access or spread immediately. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos Threat Graphs](https://docs.sophos.com/central/customer/help/en-Us/ManageYourProducts/ThreatAnalysisCenter/ThreatGraphs/index.html)
