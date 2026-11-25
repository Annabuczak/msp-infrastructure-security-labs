# INC-006 | Repeated malicious website detections

[All scenarios](../README.md#scenario-index)

**Technology:** Sophos Web Protection / XDR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Repeated attempts to connect to malicious domain.

## Investigation

Review timestamps, initiating process, browser extensions, installed software, related detections and other endpoints.

## Simulated root cause

Unwanted extension redirects browser traffic.

## Proposed resolution

Remove unauthorised extension, scan endpoint, review browser policies and potential credential exposure.

## Verification plan

Confirm detections cease and protection remains active.

## Skills covered

Web security, indicator analysis, remediation

## Diagnostic interpretation and escalation

Determine whether the browser, an extension or another process initiated the traffic. Preserve the extension ID and installation source before removal. Blocked connections do not prove successful compromise, and disappearance of alerts is meaningful only if telemetry still reports. Escalate evidence of credential theft or persistence.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
