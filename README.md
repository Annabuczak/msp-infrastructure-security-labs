# MSP Infrastructure & Security Labs

Twenty fictional troubleshooting scenarios for developing infrastructure and security investigation skills. The cases cover Windows, Active Directory, FortiGate, Sophos Central/XDR, incident response and Five9.

**Evidence status: all 20 cases are simulations and have not been executed.** Commands and example observations illustrate a method. This repository does not document real client tickets, verified remediation results or professional achievements.

## Start here

- [Lab environment and prerequisites](docs/lab-environment.md)
- [Diagnostic command reference](docs/command-reference.md)
- [Evidence and privacy policy](docs/evidence-policy.md)
- [Ticket template](templates/ticket-template.md)
- [Evidence folder guidance](evidence/README.md)
- [Technical review and limitations](docs/review-notes.md)

## Ticket index

| ID | Scenario | Area | Status |
| --- | --- | --- | --- |
| 01 | [Internal application fails to resolve](tickets/01-dns-client-misconfiguration.md) | Windows and DNS | Simulation; not executed |
| 02 | [Workstation receives an APIPA address](tickets/02-dhcp-apipa.md) | Windows and DHCP | Simulation; not executed |
| 03 | [Account repeatedly locks after a password change](tickets/03-ad-account-lockout.md) | Active Directory | Simulation; not executed |
| 04 | [User cannot access a shared folder](tickets/04-smb-permissions.md) | Windows permissions | Simulation; not executed |
| 05 | [Business application service will not start](tickets/05-windows-service-failure.md) | Windows services | Simulation; not executed |
| 06 | [New application traffic is denied by FortiGate](tickets/06-fortigate-policy-denial.md) | FortiGate | Simulation; not executed |
| 07 | [IPsec tunnel is up but a subnet is unreachable](tickets/07-ipsec-tunnel-up-no-access.md) | FortiGate | Simulation; not executed |
| 08 | [Guest Wi-Fi can reach an internal service](tickets/08-guest-vlan-isolation.md) | Network segmentation | Simulation; not executed |
| 09 | [Sophos Central reports a device as offline](tickets/09-sophos-offline-device.md) | Sophos Central | Simulation; not executed |
| 10 | [Endpoint has an unexpected security policy](tickets/10-sophos-policy-assignment.md) | Sophos Central | Simulation; not executed |
| 11 | [Suspicious PowerShell alert requires triage](tickets/11-sophos-suspicious-powershell.md) | Sophos XDR and response | Simulation; not executed |
| 12 | [Live Discover query returns no results](tickets/12-xdr-no-query-results.md) | Sophos XDR | Simulation; not executed |
| 13 | [Business file is quarantined](tickets/13-sophos-false-positive.md) | Endpoint security | Simulation; not executed |
| 14 | [Suspected ransomware activity on an endpoint](tickets/14-ransomware-containment.md) | Incident response | Simulation; not executed |
| 15 | [User reports a phishing link and password entry](tickets/15-phishing-account-response.md) | Incident response | Simulation; not executed |
| 16 | [Five9 agent cannot complete web sign-in](tickets/16-five9-web-login.md) | Five9 | Simulation; not executed |
| 17 | [Five9 desktop opens but softphone is unavailable](tickets/17-five9-softphone-not-running.md) | Five9 | Simulation; not executed |
| 18 | [Five9 call connects with one-way audio](tickets/18-five9-one-way-audio.md) | Five9 and FortiGate | Simulation; not executed |
| 19 | [Five9 calls have intermittent audio gaps](tickets/19-five9-intermittent-audio.md) | Five9 | Simulation; not executed |
| 20 | [Agent is signed in but receives no inbound calls](tickets/20-five9-no-inbound-calls.md) | Five9 | Simulation; not executed |

## Working through a case

Read the competing explanations before choosing a fix. Work in an isolated, authorised lab, confirm versions and permissions, and record what each test can and cannot establish. Apply one scoped change at a time, retain a rollback plan and test the affected service afterward.

When a case is actually performed, add a separate dated lab record with the environment, commands, genuine outputs and limitations. Keep hypothetical observations labelled as simulations. Never replace missing results with plausible-looking logs.

## Related work

- [Existing IT support labs](https://github.com/Annabuczak/it-support-labs)
- [Network labs](https://github.com/Annabuczak/Network)
- [Cybersecurity investigations](https://github.com/Annabuczak/cyber-labs)

The existing repositories contain separate work with their own evidence status. This collection does not change or certify those records.
