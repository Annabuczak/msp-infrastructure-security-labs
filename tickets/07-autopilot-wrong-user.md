# Wrong organisational identity during laptop setup

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Windows Autopilot, Windows setup  
**Status:** Unresolved

## Issue

A new laptop displayed the wrong organisational sign-in identity during first-run setup.

## What I did

1. I reviewed the device’s user assignment in Windows Autopilot.
2. I corrected the assigned user.
3. I rebooted the device and found that the original sign-in identity still appeared.

## Findings

Changing the assigned user did not resolve the setup display during the recorded test. The remaining cause was not established.

## Outcome

The assignment was corrected, but the setup issue remained unresolved.

## Follow-up

Check device registration, the assigned deployment profile and the enrolment flow with the authorised administrator. Confirm the prerequisites and impact before resetting or deleting device records.

## Skills used

Device provisioning; Autopilot administration; recording unsuccessful changes accurately.
