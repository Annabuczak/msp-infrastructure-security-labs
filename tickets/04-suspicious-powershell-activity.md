# INC-004 | Suspicious PowerShell activity

[All scenarios](../README.md#scenario-index)

**Technology:** Sophos XDR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Unusual PowerShell execution outside maintenance hours.

## Investigation

Review detection timeline, parent/child processes, command line, user, network connections and scheduled tasks.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Get-WinEvent -LogName "Microsoft-Windows-PowerShell/Operational" -MaxEvents 100
Get-ScheduledTask
Get-NetTCPConnection
```

## Simulated root cause

Authorised maintenance script triggers behavioural detection.

## Proposed resolution

Validate script source and execution context with infrastructure team; classify based on evidence; avoid broad exclusions.

## Verification plan

Confirm authorised activity and check for additional compromise indicators.

## Skills covered

XDR, process analysis, threat triage

## Diagnostic interpretation and escalation

Correlate the parent process, full command line, account, script hash and scheduled-task definition with the approved maintenance record. Check Threat Graphs and available Live Discover data where licensed. Script-block event 4104 is available only when the relevant logging captured it; missing logs do not establish that no execution occurred. Do not run the suspicious script to inspect it.

Reference: [Sophos Threat Graphs](https://docs.sophos.com/central/customer/help/en-US/ManageYourProducts/ThreatAnalysisCenter/ThreatGraphs/index.html).

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
