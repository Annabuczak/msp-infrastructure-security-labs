# Windows slowdown linked to a heavy sync workload

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Windows, OneDrive, SharePoint, Microsoft 365 apps  
**Status:** Improved; monitoring required

## Issue

A laptop became very slow after several hours of use. Word, Excel and Explorer were affected, with high CPU and memory use.

## What I did

1. I identified a resource-intensive cloud-sync process.
2. I found an exceptionally large SharePoint folder shortcut included in OneDrive and removed the shortcut without deleting the source documents.
3. I paused sync to assess its effect on performance and reset OneDrive.
4. I resolved a long-path filename sync error and also observed a search-indexing backlog.
5. I checked that the applications reopened normally after the changes.

## Findings

Sync workload and indexing were likely contributing factors. Several interventions were made, so the improvement did not isolate a single definitive root cause.

## Outcome

Performance improved and the affected applications reopened normally. Long-term stability was not yet established.

## Follow-up

Check performance after the original several-hour period, confirm OneDrive sync health and review indexing progress. Escalate if the symptoms return rather than repeatedly resetting the client.

## Skills used

Windows troubleshooting; OneDrive/SharePoint support; protecting source documents; validation after changes.
