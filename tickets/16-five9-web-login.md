# MSP-016: Five9 agent cannot complete web sign-in

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

One fictional agent cannot reach the desktop, while peers can.

**Area:** Five9. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Identity or MFA failure; browser state; wrong login entry point; network/TLS problem; service incident.

## Investigation procedure

1. Record the exact error, UTC time, tenant region and whether SSO is used. Distinguish the web sign-in from station/voice connection.
2. Compare another authorised user and a known-good workstation without sharing credentials. Review identity logs through the identity team and provider service notices.
3. Check the supported browser/version, managed extensions, DNS and HTTPS path. Capture a sanitised error; browser HAR files may contain session tokens.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
$Five9WebHost = 'tenant-web.lab.example' # Replace with verified tenant endpoint.
Resolve-DnsName $Five9WebHost
Test-NetConnection $Five9WebHost -Port 443
```

**Simulated evidence and interpretation:** Fictional result: HTTPS connects, but SSO denies the account due to assignment. TCP success cannot validate authentication or application health.

## Root-cause reasoning

Missing application assignment is the proposed cause only if identity logs support it. A station registration error would be a different investigation.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the identity owner restore approved assignment after checking access entitlement. Preserve previous assignment for rollback; do not bypass MFA.

## Validation and closure criteria

Verify sign-in, required desktop access and the separate voice-station connection.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate identity policy issues to the identity team, or widespread application failure to Five9 support with sanitised correlation details. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Five9 technical requirements](https://documentation.five9.com/bundle/technical-reqs/page/technical-reqs/landing-technical-reqs.htm)
