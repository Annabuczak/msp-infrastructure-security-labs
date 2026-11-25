# INC-013 | One-way audio and poor call quality

[All scenarios](../README.md#scenario-index)

**Technology:** Five9 / VoIP

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Agents experience distorted audio and dropped calls.

## Investigation

Collect timestamps, check headset, call metrics, latency, jitter, loss, firewall changes and vendor network requirements.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
ipconfig /all
ping -n 50 192.0.2.1
pathping test-destination.example
Get-NetAdapterStatistics
```

## Simulated root cause

Congested wireless network.

## Proposed resolution

Test wired connection, investigate utilisation and review QoS with network team.

## Verification plan

Test inbound/outbound calls and monitor quality.

## Skills covered

VoIP, QoS, packet loss

## Diagnostic interpretation and escalation

Treat one-way audio and degraded quality as separate symptoms. One-way audio warrants microphone permissions, selected devices and media-path/NAT checks; congestion is only one possibility for poor quality. Compare wired and wireless calls and use available call-media statistics. Ping/pathping are supporting observations, not measurements of the actual media stream. Use the current Five9 requirements for the region and voice mode; do not guess port ranges or disable inspection broadly.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
