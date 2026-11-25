# MSP-015: User reports a phishing link and password entry

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional user reports entering credentials into a suspicious site.

**Area:** Incident response. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Credential disclosure; session-token theft; downloaded malware; a mistaken report.

## Investigation procedure

1. Record what the user did, the UTC timeline and whether MFA prompts or downloads occurred. Preserve the message and headers through approved tooling; do not open the link.
2. Ask the identity responder to review sign-ins, MFA changes, session activity and mailbox rules where applicable. Examine the endpoint if a file ran.
3. Correlate message delivery across the authorised scope. Keep recipient information, message bodies and tokens out of the portfolio.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
# Optional: hash a safely exported message for evidence tracking.
# Hashing establishes file identity, not whether an email is malicious.
Get-FileHash 'C:\Lab\reported-message.eml' -Algorithm SHA256
```

**Simulated evidence and interpretation:** Fictional inputs: password entry reported; an unfamiliar sign-in follows. Location alone is not proof of compromise; correlate device, session and authentication details.

## Root-cause reasoning

Credential exposure is reported; account misuse remains to be established. Do not assert malware execution or data theft without evidence.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

The identity responder resets exposed credentials and revokes applicable sessions, reviews authentication methods and removes confirmed malicious persistence. Coordinate endpoint containment if warranted. Do not restore compromised credentials as rollback.

## Validation and closure criteria

Verify intended access is restored, malicious rules/methods are removed and new suspicious activity is absent during the agreed monitoring period.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate confirmed access, sensitive data exposure or privileged accounts to the incident lead. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Get-WinEvent](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent)
