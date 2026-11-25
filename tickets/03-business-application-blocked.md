# INC-003 | Business application blocked

[All tickets](../README.md#ticket-index)

**Technology:** Sophos Intercept X

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Updated component triggers detection.

## Response procedure

Validate with vendor/security team; submit suspected false positive; narrowly scope approved exception if necessary.

## Verification checks

Confirm application launches without weakening unrelated protection.

## Skills covered

Application control, hashing, false-positive analysis

## Additional diagnostic guidance

Separate malware, exploit prevention and application-control detections: their remediation options differ. A valid signature or familiar filename does not prove a file is safe. Preserve the detection ID, hash and vendor evidence before deciding whether an exception is appropriate. Give any approved exception an owner, scope and review date.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
