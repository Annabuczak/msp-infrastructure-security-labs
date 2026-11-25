# Recurring VPN sign-in and disconnections

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Managed VPN client  
**Status:** Under investigation

## Issue

A user reported repeated VPN sign-in prompts and intermittent disconnections.

## What I did

1. I investigated whether the client’s auto-connect configuration could be changed locally.
2. The centrally managed options were not visible to me.
3. I identified that specialist management permissions were needed to continue the configuration review.

## Findings

Repeated authentication prompts and dropped connections may be separate symptoms. Neither an authentication-policy fault nor a transport fault was confirmed. The source notes do not name the VPN product.

## Outcome

I identified the management-access limitation. No VPN policy change or confirmed resolution was recorded.

## Follow-up

Provide timestamps, client version and logs to the authorised VPN administrator. Review the relevant policy and connection behaviour before changing authentication or auto-connect settings.

## Skills used

VPN support; recognising administration boundaries; structured escalation.
