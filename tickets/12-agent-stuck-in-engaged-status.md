# INC-012 | Agent stuck in Engaged status

[All tickets](../README.md#ticket-index)

**Technology:** Five9

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

## Incident description

Agent cannot receive further calls after completing interaction.

## Investigation

Check agent state, outstanding interaction, connectivity, affected users and supervisor reset options.

## Root cause assessment

Interrupted session fails to update state.

## Response procedure

Clear outstanding interaction using supported procedure; reconnect session; escalate persistent lock to supervisor/vendor.

## Verification checks

Confirm Ready status and inbound call completion.

## Skills covered

Agent states, session management

## Additional diagnostic guidance

Check the exact state label in the deployed agent application. Distinguish an active voice interaction, hold or consultation, wrap-up work and a stale session. Capture the interaction ID and timestamps privately. Do not reset a session while a customer interaction is active. Use supervisor or vendor-supported recovery, then test routing and return to the expected available state.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
