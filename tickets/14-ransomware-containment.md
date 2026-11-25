# MSP-014: Suspected ransomware activity on an endpoint

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional endpoint reports rapid file changes and a ransomware-related alert.

**Area:** Incident response. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Active encryption; prevented malicious activity; legitimate bulk file changes; misleading user report.

## Investigation procedure

1. Treat credible active encryption as urgent. Notify the incident lead and preserve alert details, UTC times and affected resources without delaying containment.
2. Use authorised endpoint isolation when available and verify it took effect. If the console cannot act, coordinate network containment. Consider shared storage and account access separately.
3. Identify affected endpoints, accounts and shares. Preserve investigation records and seek specialist direction for forensic collection; do not reboot or wipe reflexively.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
# Low-impact context collection only, if it will not delay containment.
Get-Date -Format o
Get-NetTCPConnection -State Established |
    Select-Object LocalAddress,LocalPort,RemoteAddress,RemotePort,OwningProcess
```

**Simulated evidence and interpretation:** Fictional timeline: alert received at T0; isolation requested at T+2 minutes; enforcement verified at T+3. These are exercise timings, not an achievement or response metric.

## Root-cause reasoning

Root cause is unknown at triage. An alert does not establish initial access or prove every affected device has been found.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Follow the incident lead's containment and recovery plan. Test clean backups before restoration, address persistence and exposed credentials, and rebuild when justified. Isolation removal is a recovery decision, not routine rollback.

## Validation and closure criteria

Verify containment, known scope, clean recovery tests and monitoring coverage before authorising reconnection. Document unresolved questions.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate immediately to incident response; include backup/storage owners and business continuity contacts as directed. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos isolation](https://docs.sophos.com/central/customer/help/en-US/ManageYourProducts/GlobalSettings/ProtectionRemediation/AllowBlock/Network/IsolatedComputers/index.html)
