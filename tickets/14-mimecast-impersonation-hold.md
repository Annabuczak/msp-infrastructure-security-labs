# Mimecast impersonation hold on a legitimate newsletter

[All tickets](../README.md#tickets)

**Date:** 10 November 2026  
**Systems:** Mimecast Email Security, Exchange Online  
**Status:** Held message delivered; new-message test pending

## Issue

An external newsletter was held by Mimecast Impersonation Protection. The requester wanted mail from that sending domain permitted.

## What I did

1. I reviewed Exchange mail-flow rules and initially found no matching message in Exchange message trace.
2. In Mimecast, I found an existing mailbox-specific impersonation bypass and located the held newsletter in Message Tracking.
3. I reviewed the hold indicators: a targeted dictionary match and a Reply-To mismatch associated with the campaign address.
4. I inspected SPF, DKIM and DMARC results, which passed, and recorded a spam score of 0.
5. I added a domain-scoped Permitted Senders policy and a separate Impersonation Protection Bypass for internal recipients, leaving the existing mailbox-specific policy in place.
6. I released the held newsletter and confirmed a Delivered status in Mimecast Message Tracking. I did not create an Exchange transport bypass rule.

## Findings

The recorded hold was caused by impersonation indicators rather than failed sender authentication. Passing authentication supported the investigation but did not, by itself, guarantee the message was safe. The notes identify potential overlap between the permitted-sender handling and the additional bypass; necessity and effective matching remained to be reviewed.

## Outcome

The original held message was released and marked Delivered by Mimecast. The effect of the changed policies on a fresh incoming message was not yet verified.

## Follow-up

Obtain a new test message and verify its processing and recipient receipt. Confirm the security owner’s approval, review the domain-wide scope and whether both exceptions are needed, and reduce unnecessary bypass coverage. The changes recorded here are a case history, not a recommended default allowlisting procedure.

## Skills used

Mimecast tracking; authentication-header analysis; security-policy administration; delivery verification.
