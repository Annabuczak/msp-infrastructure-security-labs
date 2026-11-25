# INC-012 | Agent stuck in Engaged status

[All scenarios](../README.md#scenario-index)

**Technology:** Five9

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Agent cannot receive further calls after completing interaction.

## Investigation

Check agent state, outstanding interaction, connectivity, affected users and supervisor reset options.

## Simulated root cause

Interrupted session fails to update state.

## Proposed resolution

Clear outstanding interaction using supported procedure; reconnect session; escalate persistent lock to supervisor/vendor.

## Verification plan

Confirm Ready status and inbound call completion.

## Skills covered

Agent states, session management

## Diagnostic interpretation and escalation

Check the exact state label in the deployed agent application. Distinguish an active voice interaction, hold or consultation, wrap-up work and a stale session. Capture the interaction ID and timestamps privately. Do not reset a session while a customer interaction is active. Use supervisor or vendor-supported recovery, then test routing and return to the expected available state.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
