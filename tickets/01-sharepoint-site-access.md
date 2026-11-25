# SharePoint site ownership and access change

[All tickets](../README.md#tickets)

**Date:** 22 October 2026  
**Systems:** SharePoint Online, Microsoft 365  
**Status:** Completed

## Issue

A requester needed an existing owner removed from a SharePoint communication site while keeping that person’s email account active.

## What I did

1. I opened SharePoint Admin Centre and identified the correct communication site.
2. I reviewed the existing owners and site access.
3. I updated the requested ownership and access permissions without disabling the Microsoft 365 account.
4. I confirmed completion with the requester.

## Findings

This was a service-specific access change, rather than an account deactivation. Changing the SharePoint permissions met the request while preserving the mailbox.

## Outcome

The site permissions were updated and the email account remained active. Completion was confirmed with the requester.

## Follow-up

The weekly notes also identify an effective-permissions check as a follow-up. They do not record a separate test of every possible access path; I would check any remaining group-based access before treating access removal as comprehensively validated.

## Skills used

SharePoint administration; access control; preserving unrelated services during a change.
