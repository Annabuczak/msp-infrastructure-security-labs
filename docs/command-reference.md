# Diagnostic command reference

These examples have been reviewed as documentation, not executed against product environments. Commands in tickets are diagnostic examples, not an automation script. Do not paste mixed Windows/FortiGate examples into a single shell.

## Windows

Confirm target names, modules and permissions. A failed query may indicate missing permissions, absent logs or unavailable services rather than the suspected fault. Test-NetConnection with -Port tests TCP; it does not test UDP media, application login or complete TLS behaviour. ICMP failure alone does not establish an outage.

Use narrow event filters and bounded result counts. Event messages and process command lines can contain sensitive data. PowerShell event 4104 depends on relevant logging and retention; do not infer historical coverage from a successful query today.

## FortiGate bounded flow debug

Coordinate with the firewall administrator before using debug: reset/disable commands can interrupt someone else's diagnostic session. Select the correct VDOM, confirm source address and generate a new test connection. Hardware offload or an existing session may limit visibility; absence from debug does not establish absence of traffic. Do not globally disable acceleration or clear all sessions to make an example work.

```text
diagnose debug reset
diagnose debug flow filter clear
diagnose debug flow filter addr 10.20.10.50
diagnose debug flow filter port 443
diagnose debug flow show function-name enable
diagnose debug flow trace start 20
diagnose debug enable
```

Generate one approved test, then stop promptly, including when no output appears:

```text
diagnose debug disable
diagnose debug flow trace stop
diagnose debug reset
```

A bounded packet capture example:

```text
diagnose sniffer packet any 'host 10.20.10.50 and tcp port 443' 4 20 l
```

Stop with Ctrl+C if the packet limit is not reached. Inspect source/destination, interface and direction together. Keep diagnostic output private until reviewed.

Reference: [Fortinet CLI troubleshooting](https://docs.fortinet.com/document/fortigate/7.6.0/cli-troubleshooting-cheat-sheet/420966/cli-troubleshooting-cheat-sheet).

## Sophos

Use current tenant roles and supported diagnostic collection. Live Discover endpoint queries inspect connected devices; Data Lake queries search uploaded data and have separate schemas and coverage. Live Response is an interactive response capability, not another name for Live Discover. Do not assume a read-only/help-desk role can isolate devices.

Manual administrative isolation and policy-driven isolation should be investigated separately. A request to isolate is not proof the endpoint enforced it. Record acknowledgement and recovery authorisation. Avoid broad exclusions or disabling protection to make troubleshooting easier.

References: [Live Discover](https://docs.sophos.com/central/customer/help/en-us/ManageYourProducts/ThreatAnalysisCenter/LiveDiscover/index.html), [roles](https://docs.sophos.com/central/customer/help/en-Us/ManageYourProducts/GlobalSettings/AccessControl/Roles/AdministrationRoles/AdminRoleSummary/index.html), [administrative isolation](https://docs.sophos.com/central/customer/help/en-US/ManageYourProducts/GlobalSettings/ProtectionRemediation/AllowBlock/Network/IsolatedComputers/index.html).

## Five9

Separate web authentication, station connection, routing eligibility and media quality. Capture the actual station type and use its current network requirements. Do not apply an installed softphone's assumptions to WebRTC. SIP/inspection changes must be scoped and coordinated with the network owner because other voice services may depend on existing behaviour.

Use approved test calls. Share only sanitised timestamps, diagnostic versions and test-call identifiers with support. Do not publish recordings, caller numbers or browser session tokens.

Reference: [Five9 technical requirements](https://documentation.five9.com/bundle/technical-reqs/page/technical-reqs/landing-technical-reqs.htm).
