# MSP-010: Endpoint has an unexpected security policy

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional laptop does not appear to receive the intended protection settings.

**Area:** Sophos Central. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Wrong group assignment; higher-priority policy; user/device targeting mismatch; offline endpoint; duplicate record.

## Investigation procedure

1. Confirm device identity, group and last contact before comparing policy names.
2. Inspect enabled policies, targeting and effective assignment in the current tenant. Record intended settings and actual endpoint status.
3. Compare a known-good device in the same intended group. Check audit history for recent assignment or policy edits.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-Service | Where-Object DisplayName -Like '*Sophos*' |
    Select-Object Name,Status
```

**Simulated evidence and interpretation:** Fictional console summary: LAB-WS02 belongs to a pilot group with a different policy. Local service state cannot determine the effective Central policy.

## Root-cause reasoning

Incorrect group placement is the assumed cause. Policy names alone do not establish which configuration is effective.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Correct the verified group or targeted assignment through the policy owner. Record prior membership and test one device first; avoid weakening a global policy.

## Validation and closure criteria

Confirm the intended settings after synchronisation, and check other pilot devices have not changed unexpectedly.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate policy precedence ambiguity or a protection downgrade to the endpoint owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos administration roles](https://docs.sophos.com/central/customer/help/en-Us/ManageYourProducts/GlobalSettings/AccessControl/Roles/AdministrationRoles/AdminRoleSummary/index.html)
