# MSP-008: Guest Wi-Fi can reach an internal service

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

An untrusted fictional guest device can reach a lab file server.

**Area:** Network segmentation. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

SSID mapped to the trusted VLAN; broad inter-VLAN policy; unintended bridge; an incomplete isolation test.

## Investigation procedure

1. Record SSID, client IP, VLAN mapping and permitted guest services. Different SSIDs do not establish isolation.
2. Test a known listening internal TCP service from both an authorised trusted host and the guest. Inspect the actual forwarding path and firewall logs.
3. Review IPv4 and IPv6 paths and AP/client isolation separately. A failed ping alone does not establish that all internal access is blocked.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```text
Get-NetIPConfiguration
Test-NetConnection 10.20.20.10 -Port 445
# FortiGate CLI, correct VDOM:
diagnose sniffer packet any 'host 10.20.40.50 and host 10.20.20.10' 4 20 l
```

**Simulated evidence and interpretation:** Fictional result: TCP 445 succeeds from the guest before a policy correction. Afterward it fails while a trusted test still succeeds.

## Root-cause reasoning

The scenario assumes an overly broad guest-to-server policy. Confirm the matched policy and path; the same symptoms could arise from incorrect VLAN mapping.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Correct guest policy to the approved service matrix, retaining required DNS/DHCP and internet access. Save the old rules for rollback and check rule order.

## Validation and closure criteria

Use positive controls on known services, test IPv6 where enabled, and verify guest internet access. Document precisely which paths were tested.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate shared VLANs, bridge design or unknown IPv6 paths to the network owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [FortiOS 7.6 CLI troubleshooting](https://docs.fortinet.com/document/fortigate/7.6.0/cli-troubleshooting-cheat-sheet/420966/cli-troubleshooting-cheat-sheet)
