# Multiple users unable to sign in to a website

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Web browsers, Microsoft identity administration  
**Status:** Investigated; root cause unconfirmed

## Issue

Several employees could not sign in to a third-party website.

## What I did

1. I tested private browsing as part of the investigation.
2. I reviewed the available identity application records.
3. I did not find a corresponding enterprise application in the tenant records I checked.

## Findings

The missing enterprise-application entry did not by itself establish the website’s authentication method or explain the failure. The private-browsing test result was not captured in the notes.

## Outcome

Initial browser and identity checks were completed. No successful sign-in or confirmed fix was recorded.

## Follow-up

Collect the exact error and UTC timestamp, compare browsers and networks, and confirm how the service authenticates users. Check the provider’s status and the relevant filtering or SSO configuration before escalating.

## Skills used

Browser troubleshooting; identity investigation; scoping a multi-user incident.
