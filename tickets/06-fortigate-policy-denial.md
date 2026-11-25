# MSP-006: New application traffic is denied by FortiGate

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional user VLAN cannot reach a newly approved internal HTTPS application.

**Area:** FortiGate. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Missing policy; wrong address object; routing failure; listener unavailable; inspection rejection.

## Investigation procedure

1. Record source, destination, port, time, VDOM and intended rule. Verify the server is listening from an authorised test host.
2. Inspect traffic logs and the matching policy, including interfaces and object membership. Review routes before adding a rule.
3. Use a brief filtered capture and, if needed, the bounded debug procedure in the command reference. Correlate logs to the same connection.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```text
get system status
get router info routing-table all
diagnose sniffer packet any 'host 10.20.10.50 and host 10.20.20.30 and tcp port 443' 4 20 l
```

**Simulated evidence and interpretation:** Fictional evidence: the application address is absent from the intended destination object, and the flow is denied. No real policy ID or firewall output is supplied.

## Root-cause reasoning

The destination object omission is the intended cause only after route and service checks support it.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Back up the relevant policy/object configuration. Add only the approved destination/service in a reviewed change. Restore that change if the application test fails; avoid a broad temporary allow rule.

## Validation and closure criteria

Repeat the application transaction, confirm the intended rule matches, and check unrelated destinations remain blocked.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate policy design, inspection changes or uncertain routing to the firewall owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [FortiOS 7.6 CLI troubleshooting](https://docs.fortinet.com/document/fortigate/7.6.0/cli-troubleshooting-cheat-sheet/420966/cli-troubleshooting-cheat-sheet)
