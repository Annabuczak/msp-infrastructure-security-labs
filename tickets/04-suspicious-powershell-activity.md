# INC-004 | Suspicious PowerShell activity

[All tickets](../README.md#ticket-index)

**Technology:** Sophos XDR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Authorised maintenance script triggers behavioural detection.

## Response procedure

Validate script source and execution context with infrastructure team; classify based on evidence; avoid broad exclusions.

## Verification checks

Confirm authorised activity and check for additional compromise indicators.

## Skills covered

XDR, process analysis, threat triage

## Additional diagnostic guidance

Correlate the parent process, full command line, account, script hash and scheduled-task definition with the approved maintenance record. Check Threat Graphs and available Live Discover data where licensed. Script-block event 4104 is available only when the relevant logging captured it; missing logs do not establish that no execution occurred. Do not run the suspicious script to inspect it.

Reference: [Sophos Threat Graphs](https://docs.sophos.com/central/customer/help/en-US/ManageYourProducts/ThreatAnalysisCenter/ThreatGraphs/index.html).

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
