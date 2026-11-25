# Messages arriving in Gmail spam

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Microsoft 365, Outlook, CRM email, DNS  
**Status:** Investigation in progress

## Issue

Several users reported that messages sent through Outlook and a CRM were reaching Gmail spam folders.

## What I did

1. I confirmed examples of messages being delivered to spam.
2. I checked the published SPF record and recorded it as valid and within the permitted DNS lookup count.
3. I reviewed DMARC and recorded a valid reject policy with full enforcement.
4. I found that custom-domain DKIM was disabled in Microsoft 365 and the required selector CNAME records were missing.
5. I recorded the expected DNS values internally for an authorised administrator.

## Findings

The missing Microsoft 365 DKIM configuration was an actionable finding, but it did not prove the cause of spam placement. The Outlook and CRM sending paths needed separate authentication checks.

## Outcome

The investigation identified a configuration gap. I did not change DNS or confirm that Gmail inbox placement had improved.

## Follow-up

Obtain a recipient-side “Show original” header, compare authentication and alignment for each sending path, review reputation and content factors, and escalate the DKIM configuration. Retest delivery after any approved change.

## Skills used

Email authentication; DNS review; distinguishing a configuration issue from a proven root cause.
