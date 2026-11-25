# MSP-009: Sophos Central reports a device as offline

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional workstation is in use but its management record is stale.

**Area:** Sophos Central. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Device offline; duplicate inventory record; agent health issue; DNS/proxy/TLS path failure; incorrect system time.

## Investigation procedure

1. Match the console device identity to the local endpoint and record last contact. Check for a renamed or duplicated device record.
2. Inspect local agent health, relevant logs, system time and connectivity to the tenant's documented service endpoints. Compare another device using the same egress path.
3. Use supported Sophos diagnostics when basic checks do not explain the issue. Collect only necessary logs and redact tokens and identifiers before sharing.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-Service | Where-Object DisplayName -Like '*Sophos*' |
    Select-Object Name,DisplayName,Status
Get-Date
w32tm /query /status
Get-DnsClientServerAddress
netsh winhttp show proxy
```

**Simulated evidence and interpretation:** Invented observation: affected devices share a proxy change; management TLS connections fail. A running service is not proof of healthy protection or communication.

## Root-cause reasoning

Proxy-related connectivity is the intended hypothesis. Correlate agent errors and proxy decisions before concluding; the listed proxy command does not reveal every application proxy setting.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the network owner restore the approved vendor connectivity path. Do not disable tamper protection or uninstall the agent as the first step. Preserve prior proxy settings for rollback.

## Validation and closure criteria

Verify fresh check-in, protection health, policy status and updates after the expected sync interval.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate a prolonged protection gap or unsupported repair to endpoint security and Sophos support. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos administration roles](https://docs.sophos.com/central/customer/help/en-Us/ManageYourProducts/GlobalSettings/AccessControl/Roles/AdministrationRoles/AdminRoleSummary/index.html)
