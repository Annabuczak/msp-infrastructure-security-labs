# INC-013 | One-way audio and poor call quality

[All tickets](../README.md#ticket-index)

**Technology:** Five9 / VoIP

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Congested wireless network.

## Response procedure

Test wired connection, investigate utilisation and review QoS with network team.

## Verification checks

Test inbound/outbound calls and monitor quality.

## Skills covered

VoIP, QoS, packet loss

## Additional diagnostic guidance

Treat one-way audio and degraded quality as separate symptoms. One-way audio warrants microphone permissions, selected devices and media-path/NAT checks; congestion is only one possibility for poor quality. Compare wired and wireless calls and use available call-media statistics. Ping/pathping are supporting observations, not measurements of the actual media stream. Use the current Five9 requirements for the region and voice mode; do not guess port ranges or disable inspection broadly.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
