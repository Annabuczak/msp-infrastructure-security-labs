# Infrastructure & Security Engineering Portfolio

20 simulated Tier 1 and Tier 2 troubleshooting cases covering endpoint protection, incident response, firewall policy, remote access, identity, email security and contact-centre infrastructure.

These scenarios develop structured investigation, root cause analysis, least privilege, containment and verification. They are adapted from my Notion incident library. **They have not been lab-tested and do not represent completed production incidents.** Commands are examples; no output or successful remediation is claimed.

## Scenario index

| ID | Scenario | Technology |
| --- | --- | --- |
| INC-001 | [Malware detection and endpoint isolation](tickets/01-malware-detection-and-endpoint-isolation.md) | Sophos Central / Intercept X |
| INC-002 | [Endpoint not communicating with Central](tickets/02-endpoint-not-communicating-with-central.md) | Sophos Central |
| INC-003 | [Business application blocked](tickets/03-business-application-blocked.md) | Sophos Intercept X |
| INC-004 | [Suspicious PowerShell activity](tickets/04-suspicious-powershell-activity.md) | Sophos XDR |
| INC-005 | [Endpoint protection service stopped](tickets/05-endpoint-protection-service-stopped.md) | Sophos Central |
| INC-006 | [Repeated malicious website detections](tickets/06-repeated-malicious-website-detections.md) | Sophos Web Protection / XDR |
| INC-007 | [Intermittent VPN disconnections](tickets/07-intermittent-vpn-disconnections.md) | FortiClient / FortiGate |
| INC-008 | [Device network access denied](tickets/08-device-network-access-denied.md) | FortiGate / DHCP / VLANs |
| INC-009 | [Legitimate website blocked](tickets/09-legitimate-website-blocked.md) | FortiGuard |
| INC-010 | [Denied firewall traffic](tickets/10-denied-firewall-traffic.md) | FortiGate |
| INC-011 | [VPN authentication failure](tickets/11-vpn-authentication-failure.md) | FortiClient / FortiGate / MFA |
| INC-012 | [Agent stuck in Engaged status](tickets/12-agent-stuck-in-engaged-status.md) | Five9 |
| INC-013 | [One-way audio and poor call quality](tickets/13-one-way-audio-and-poor-call-quality.md) | Five9 / VoIP |
| INC-014 | [Incorrect IVR call routing](tickets/14-incorrect-ivr-call-routing.md) | Five9 / IVR |
| INC-015 | [Guest blocked by Conditional Access](tickets/15-guest-blocked-by-conditional-access.md) | Entra ID / Teams |
| INC-016 | [BitLocker compliance failure](tickets/16-bitlocker-compliance-failure.md) | Intune / Entra / BitLocker |
| INC-017 | [Shared mailbox missing in Outlook](tickets/17-shared-mailbox-missing-in-outlook.md) | Exchange Online |
| INC-018 | [Suspicious Entra sign-in](tickets/18-suspicious-entra-sign-in.md) | Entra ID / MFA |
| INC-019 | [Email held by impersonation protection](tickets/19-email-held-by-impersonation-protection.md) | Mimecast / Exchange |
| INC-020 | [Wi-Fi connected but no internet](tickets/20-wi-fi-connected-but-no-internet.md) | Windows / DHCP / DNS |

## Using the cases

Each case contains the incident description, investigation, assumed root cause, proposed resolution and verification plan. Diagnostic notes explain what the available checks can establish and when to escalate. Priority and support tier are scenario values, not universal service-level definitions.

Before executing a scenario, record the product version, deployment mode, licence and authorised lab scope. Use approved changes and a rollback plan where needed. Add sanitised evidence and an actual outcome only after completing the exercise. Keep customer data, credentials, recovery keys and production logs out of this repository.

## Workplace experience

My anonymised workplace tickets are published separately in [IT Support Troubleshooting Cases](https://github.com/Annabuczak/it-support-troubleshooting-cases).

## Technical references

- INC-004: [Sophos Threat Graphs](https://docs.sophos.com/central/customer/help/en-US/ManageYourProducts/ThreatAnalysisCenter/ThreatGraphs/index.html) for investigation context and related threat hunting.
- INC-010: [FortiOS 7.4.7 debug flow commands](https://docs.fortinet.com/document/fortigate/7.4.7/cli-reference/159376337/diagnose-debug); use the reference matching the installed version.
- INC-013: [Five9 Voice Insights Agent Health guide](https://documentation-be.five9.com/bundle/voice-insights-agent-health-administrators-guide/raw/resource/enus/voice-insights-agent-health-administrators-guide.pdf) for audio events and troubleshooting context.
- INC-017: [Microsoft mailbox permissions](https://learn.microsoft.com/en-us/exchange/recipients/mailbox-permissions) explains the group-based automapping limitation.
- INC-018: [Microsoft emergency access revocation](https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access) explains why application session termination can differ.
