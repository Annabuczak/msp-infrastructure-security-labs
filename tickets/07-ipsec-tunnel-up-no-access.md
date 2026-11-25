# MSP-007: IPsec tunnel is up but a subnet is unreachable

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional branch can establish a tunnel but cannot reach a new server subnet.

**Area:** FortiGate. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Missing route; Phase 2 selector mismatch; firewall policy; unintended NAT; remote return route.

## Investigation procedure

1. Separate IKE establishment from Phase 2/IPsec SAs and application reachability. Record both protected subnets and the failed service.
2. Compare selectors, routes and policies at both peers. Check whether the deployment is route-based and whether selectors are narrow or broad.
3. Capture a single test flow on both sides and compare tunnel counters. A tunnel status alone does not demonstrate bidirectional data transfer.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```text
get vpn ipsec tunnel summary
diagnose vpn tunnel list
get router info routing-table all
diagnose sniffer packet any 'host 10.20.10.50 and host 10.30.20.30' 4 20 l
```

**Simulated evidence and interpretation:** Invented observations: local packets enter the tunnel; the remote side lacks a route back to the client subnet. This is a scenario input, not captured output.

## Root-cause reasoning

Missing remote return routing is the teaching hypothesis. Rule out selector and policy mismatches before attributing the failure.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Coordinate a narrowly scoped routing correction with the remote owner. Preserve route settings and avoid restarting all tunnels; changes may affect other services.

## Validation and closure criteria

Confirm a complete request/response and increasing traffic counters in both directions for the intended subnet. Recheck existing VPN services.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate peer access limitations or overlapping address ranges to network engineering. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [FortiOS 7.6 CLI troubleshooting](https://docs.fortinet.com/document/fortigate/7.6.0/cli-troubleshooting-cheat-sheet/420966/cli-troubleshooting-cheat-sheet)
