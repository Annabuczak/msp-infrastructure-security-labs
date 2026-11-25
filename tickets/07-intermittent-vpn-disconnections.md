# INC-007 | Intermittent VPN disconnections

[All scenarios](../README.md#scenario-index)

**Technology:** FortiClient / FortiGate

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Remote user loses VPN access repeatedly.

## Investigation

Review client and gateway logs, version, timeouts, scope, packet loss and alternate connection.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
ipconfig /all
ping -n 50 192.0.2.1
pathping vpn.example.com
Test-NetConnection vpn.example.com -Port 443
```

## Simulated root cause

Wireless packet loss.

## Proposed resolution

Test Ethernet, investigate interference; escalate persistent wired loss to ISP.

## Verification plan

Monitor extended VPN session and internal access.

## Skills covered

VPN, network diagnostics

## Diagnostic interpretation and escalation

Identify SSL VPN versus IPsec and the configured listener before testing. TCP 443 applies only when that service actually uses it and does not test an IPsec UDP tunnel. ICMP may be filtered or deprioritised. Compare wired and wireless tests at matched times; local-router loss does not by itself justify an ISP escalation.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
