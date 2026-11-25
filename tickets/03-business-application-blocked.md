# INC-003 | Business application blocked

[All scenarios](../README.md#scenario-index)

**Technology:** Sophos Intercept X

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Business application fails after update.

## Investigation

Identify executable, version, signature, origin, detection type and vendor confirmation.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Get-AuthenticodeSignature "C:\Example\App.exe"
Get-FileHash "C:\Example\App.exe" -Algorithm SHA256
```

## Simulated root cause

Updated component triggers detection.

## Proposed resolution

Validate with vendor/security team; submit suspected false positive; narrowly scope approved exception if necessary.

## Verification plan

Confirm application launches without weakening unrelated protection.

## Skills covered

Application control, hashing, false-positive analysis

## Diagnostic interpretation and escalation

Separate malware, exploit prevention and application-control detections: their remediation options differ. A valid signature or familiar filename does not prove a file is safe. Preserve the detection ID, hash and vendor evidence before deciding whether an exception is appropriate. Give any approved exception an owner, scope and review date.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
