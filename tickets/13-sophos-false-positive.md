# MSP-013: Business file is quarantined

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional user requests release of a file needed for work.

**Area:** Endpoint security. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Malware; a potentially unwanted tool; tampered installer; legitimate software incorrectly detected.

## Investigation procedure

1. Preserve the detection name, file hash, source and business justification. Do not restore or execute the item to test whether it is safe.
2. Compare the hash and signature with the approved publisher distribution. Review process activity and related detections; a signature alone does not establish safety.
3. Have security review the case and use the approved vendor false-positive submission process. Do not upload confidential files to public analysis services.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
# Only for an accessible approved comparison file; do not restore quarantine.
Get-FileHash 'C:\Lab\ApprovedInstaller.msi' -Algorithm SHA256
Get-AuthenticodeSignature 'C:\Lab\ApprovedInstaller.msi' |
    Select-Object Status,StatusMessage,SignerCertificate
```

**Simulated evidence and interpretation:** Fictional evidence: the quarantined hash differs from the approved installer. This is a reason to investigate further, not to allowlist it.

## Root-cause reasoning

The verdict remains unresolved pending analysis. A user request is not evidence of a false positive.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Provide an approved replacement if appropriate. Any exception must be narrowly scoped, justified, time-limited and reviewed; retain a removal plan. Do not exclude an entire downloads folder.

## Validation and closure criteria

Verify the approved replacement works and protection remains enabled. Record the final vendor/security verdict separately from the initial hypothesis.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate hash mismatch, unexpected origin or related suspicious behaviour to incident response. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos Threat Graphs](https://docs.sophos.com/central/customer/help/en-Us/ManageYourProducts/ThreatAnalysisCenter/ThreatGraphs/index.html)
