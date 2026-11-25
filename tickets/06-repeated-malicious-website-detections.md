# INC-006 | Repeated malicious website detections

[All tickets](../README.md#ticket-index)

**Technology:** Sophos Web Protection / XDR

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

Repeated attempts to connect to malicious domain.

## Investigation

Review timestamps, initiating process, browser extensions, installed software, related detections and other endpoints.

## Root cause assessment

Unwanted extension redirects browser traffic.

## Response procedure

Remove unauthorised extension, scan endpoint, review browser policies and potential credential exposure.

## Verification checks

Confirm detections cease and protection remains active.

## Skills covered

Web security, indicator analysis, remediation

## Additional diagnostic guidance

Determine whether the browser, an extension or another process initiated the traffic. Preserve the extension ID and installation source before removal. Blocked connections do not prove successful compromise, and disappearance of alerts is meaningful only if telemetry still reports. Escalate evidence of credential theft or persistence.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
