# MSP-004: User cannot access a shared folder

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

One fictional user cannot open an authorised team folder.

**Area:** Windows permissions. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Missing group membership; share permissions; NTFS permissions; stale access token; DNS or SMB connectivity.

## Investigation procedure

1. Capture the exact UNC path and error. Confirm the resource owner has authorised access before changing permissions.
2. Test name resolution and TCP 445. On the file server, compare share permissions and NTFS effective access, including inherited entries and deny rules.
3. Check group membership and session age. Compare with an equivalent authorised user without copying all of that user's permissions.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Test-NetConnection fs01.lab.example -Port 445
whoami /groups
# Run on the lab file server with suitable permissions:
Get-SmbShareAccess -Name Team
(Get-Acl 'D:\Shares\Team').Access
```

**Simulated evidence and interpretation:** Fictional inputs: TCP 445 succeeds; share permissions permit the team group; the user is absent from that group. Connectivity does not establish authorisation.

## Root-cause reasoning

Missing approved group membership is the scenario hypothesis. Verify both permission layers and effective membership before concluding.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Apply the smallest approved group change and renew the user session appropriately. Record the original membership for rollback. Do not grant Everyone full control.

## Validation and closure criteria

Test the required read/write operation and confirm restricted folders remain inaccessible.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate uncertain ownership or conflicting deny entries to the file-service owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Microsoft DNS troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking/troubleshoot-dns-client-resolution-issues)
- [Test-NetConnection](https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection)
