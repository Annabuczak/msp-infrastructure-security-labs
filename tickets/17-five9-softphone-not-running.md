# MSP-017: Five9 desktop opens but softphone is unavailable

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional Windows agent can sign in but cannot connect the installed softphone.

**Area:** Five9. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Local component not running; unsupported version; blocked browser integration; station configuration; network registration failure.

## Investigation procedure

1. Confirm this deployment uses the installed softphone, not browser-only WebRTC. Record desktop integration, component version and local versus VDI installation.
2. Inspect the tray and Task Manager for the expected installed component. Verify startup settings and approved software inventory.
3. Start the approved component and recheck the desktop integration. If it runs but registration fails, collect vendor diagnostics and investigate the network/station path separately.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-Process | Where-Object ProcessName -Match 'five9|softphone' |
    Select-Object ProcessName,Id,StartTime
```

**Simulated evidence and interpretation:** Fictional input: the installed component is absent from Task Manager after reboot. The name filter is only a starting point; confirm actual executable names for the deployed package.

## Root-cause reasoning

Disabled startup is the intended cause, conditional on the correct component being installed and functioning when launched.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Restore the approved startup configuration. If repair/reinstallation is required, use the supported package and deployment process, saving configuration and rollback options.

## Validation and closure criteria

Test station connection and an authorised test call, then verify startup after an agreed restart.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate repeated startup failure, VDI placement issues or unsupported versions to the application owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Five9 Windows softphone troubleshooting](https://documentation.five9.com/bundle/virtual-desktop/page/virtual-desktop/trouble/troubleshooting-ms-windows.htm)
