# Forwarded messages missing from the inbox

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Exchange Online, Outlook  
**Status:** Partially investigated

## Issue

A user reported that important forwarded messages were not appearing in the expected inbox.

## What I did

1. I checked Exchange Online message trace for the examples provided.
2. One example had a delivery record; a different date had no matching result.
3. An older example was outside the available trace-retention window.
4. I checked mailbox delegation and noted that an online archive was unavailable.

## Findings

The examples did not share a single confirmed failure. A delivery record showed that one message reached the mailbox path, but did not establish where it was at the time of the complaint. A missing search result was inconclusive without complete sender, recipient and timing details.

## Outcome

I established different evidence for the reported examples. No recovered message or final root cause was recorded.

## Follow-up

With the mailbox owner, compare Outlook on the web, inbox rules, Deleted Items, Junk Email and recoverable items. Collect fresh examples with accurate timestamps for another trace.

## Skills used

Message tracing; retention awareness; mailbox investigation; handling incomplete evidence.
