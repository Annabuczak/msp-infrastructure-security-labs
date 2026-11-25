# Temporary holiday announcement routing

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Contact-centre IVR editor  
**Status:** Configuration awaiting validation

## Issue

An IVR needed a temporary bank-holiday announcement window from Saturday afternoon to Tuesday morning.

## What I did

1. I configured six date/time conditions in the IVR editor.
2. I combined the date boundaries using a custom AND/OR expression.
3. I identified expression syntax, timezone and boundary behaviour as validation requirements.

## Findings

The configuration was prepared, but its exact expression and the product name were not recorded in the sanitised notes. No successful production activation can be claimed from this record.

## Outcome

The routing conditions were configured and remained under validation.

## Follow-up

Test just before the start, at the start, within the window, at the end and immediately afterward. Verify the script timezone and expression grouping, then confirm both the holiday route and normal route before publication.

## Skills used

IVR configuration; Boolean conditions; time-based routing; boundary-test planning.
