# MSP-001: Internal application fails to resolve

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

One fictional workstation cannot open an internal application; colleagues can.

**Area:** Windows and DNS. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Incorrect resolver settings; a missing DNS record; VPN DNS policy; application failure after successful resolution.

## Investigation procedure

1. Record the exact hostname, error, time and affected network. Compare with a working workstation on the same VLAN.
2. Inspect configured resolvers and query the application name. Query the intended internal DNS server directly, keeping the requested record type consistent.
3. If resolution succeeds, test the application port and then the application itself. Check split DNS and VPN policy before changing settings.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-DnsClientServerAddress -AddressFamily IPv4
Resolve-DnsName app.lab.example -Type A
Resolve-DnsName app.lab.example -Type A -Server 10.20.10.10
Test-NetConnection app.lab.example -Port 443
```

**Simulated evidence and interpretation:** Default query: NXDOMAIN. Query to 10.20.10.10: 10.20.20.30. These invented observations suggest different DNS views; they do not prove the application is healthy.

## Root-cause reasoning

The exercise assumes a manually configured external resolver on the client. Confirm the interface configuration and intended policy before accepting this explanation.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Restore the approved DNS configuration on the affected interface. Record previous values for rollback; do not replace enterprise DNS with a public resolver as a permanent fix.

## Validation and closure criteria

Repeat resolution through the normal client path and open the application. Confirm internal domain resources still resolve after reconnecting.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate conflicting DNS policies or a missing authoritative record to the DNS owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Microsoft DNS troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking/troubleshoot-dns-client-resolution-issues)
- [Test-NetConnection](https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection)
