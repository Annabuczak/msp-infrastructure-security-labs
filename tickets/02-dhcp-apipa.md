# MSP-002: Workstation receives an APIPA address

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A newly connected workstation has no access to its expected subnet.

**Area:** Windows and DHCP. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

DHCP scope exhaustion; VLAN mismatch; missing relay; disconnected network; server unavailable.

## Investigation procedure

1. Confirm link state, adapter, DHCP setting and address. An address in 169.254.0.0/16 suggests link-local configuration, not a specific DHCP root cause.
2. Compare the switch port/VLAN with a working client. Ask the DHCP administrator to inspect scope utilisation, exclusions and leases.
3. If capacity exists, trace DHCP discovery and replies across the client VLAN and relay. Renew only the affected adapter during an agreed interruption.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-NetAdapter
Get-NetIPConfiguration
ipconfig /all
# On an authorised admin host with the DhcpServer module:
Get-DhcpServerv4Scope -ComputerName dc01.lab.example
Get-DhcpServerv4ScopeStatistics -ComputerName dc01.lab.example -ScopeId 10.20.10.0
```

**Simulated evidence and interpretation:** Client: 169.254.20.50 with no expected gateway. Scope statistics: no free addresses. Both values are fictional training inputs.

## Root-cause reasoning

Scope exhaustion is the intended cause only if the client reaches that scope and the server cannot allocate a lease. APIPA alone is insufficient.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the DHCP owner review address allocation and safely recover unused capacity or approve a scope redesign. Do not delete active leases or assign an arbitrary static address.

## Validation and closure criteria

Confirm a valid lease, gateway and DNS configuration; test internal and required external services. Check capacity remains adequate for additional clients.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate relay, VLAN or scope design changes to the infrastructure owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [DHCP scope inspection](https://learn.microsoft.com/en-us/powershell/module/dhcpserver/get-dhcpserverv4scope)
