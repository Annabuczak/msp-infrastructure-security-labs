# Leaver automatic reply and admin portal error

[All tickets](../README.md#tickets)

**Date:** 22 October 2026  
**Systems:** Exchange Online, Microsoft 365  
**Status:** Configuration completed

## Issue

A departing employee’s mailbox needed an automatic reply directing internal and external senders to an alternative contact.

## What I did

1. I attempted to configure the reply in Exchange Admin Centre and encountered “Parsing of Response Content Failed in Api Operations”.
2. I restarted the workstation and retried the portal.
3. I reviewed Microsoft diagnostic results showing successful browser connectivity and service endpoint checks.
4. I used Microsoft 365 Admin Centre as an alternative, reviewed the scheduling options and configured the requested reply for internal and external senders.

## Findings

The alternative admin interface allowed the mailbox change to be completed. The successful connectivity checks did not establish why the Exchange portal returned its parsing error.

## Outcome

The automatic reply was configured. No mailbox deletion was part of the request.

## Follow-up

Internal and external test messages were listed as follow-up verification. The notes do not record those test results or a confirmed fix for the original portal error.

## Skills used

Mailbox administration; offboarding support; troubleshooting administrative interfaces.
