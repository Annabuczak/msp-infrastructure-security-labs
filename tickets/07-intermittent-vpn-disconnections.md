# INC-007 | Intermittent VPN disconnections

[All tickets](../README.md#ticket-index)

**Technology:** FortiClient / FortiGate

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Wireless packet loss.

## Response procedure

Test Ethernet, investigate interference; escalate persistent wired loss to ISP.

## Verification checks

Monitor extended VPN session and internal access.

## Skills covered

VPN, network diagnostics

## Additional diagnostic guidance

Identify SSL VPN versus IPsec and the configured listener before testing. TCP 443 applies only when that service actually uses it and does not test an IPsec UDP tunnel. ICMP may be filtered or deprioritised. Compare wired and wireless tests at matched times; local-router loss does not by itself justify an ISP escalation.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
