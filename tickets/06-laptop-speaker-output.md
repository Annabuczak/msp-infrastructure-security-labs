# Laptop speakers produced no sound

[All tickets](../README.md#tickets)

**Date:** Week ending 23 October 2026  
**Systems:** Windows audio  
**Status:** Resolved; exact cause not established

## Issue

The user could not hear sound through the laptop’s built-in speakers.

## What I did

1. I checked audio during remote support and confirmed Windows Audio services were running.
2. I tested headphone output, which worked.
3. After disconnecting the headphones, built-in speaker audio resumed.

## Findings

Connecting and disconnecting headphones changed the output behaviour and restored sound. This was a successful recovery step, but the notes do not establish whether the underlying issue was routing, jack detection or a driver state.

## Outcome

The built-in speakers worked again after the headphone test.

## Follow-up

If the problem recurs, inspect the selected output device, enhancements, driver and jack-detection behaviour. Avoid describing a driver fault as confirmed without further evidence.

## Skills used

Endpoint support; audio-path isolation; distinguishing restoration from root-cause confirmation.
