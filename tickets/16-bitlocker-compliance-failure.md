# INC-016 | BitLocker compliance failure

[All tickets](../README.md#ticket-index)

**Technology:** Intune / Entra / BitLocker

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

Non-compliant laptop blocked from protected resources.

## Investigation

Review failed encryption setting, BitLocker, TPM, policies, conflicts and last check-in.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Get-BitLockerVolume
Get-Tpm
manage-bde -status
dsregcmd /status
```

## Root cause assessment

Protection suspended after firmware maintenance.

## Response procedure

Confirm recovery key escrow, resume protection using approved procedure and sync Intune.

## Verification checks

Verify protection, compliance and authorised access.

## Skills covered

TPM, encryption, endpoint compliance

## Additional diagnostic guidance

Distinguish encryption percentage from protection status: a fully encrypted volume may have protection suspended. Verify the specific Intune compliance failure and policy assignment rather than assuming suspension explains it. Confirm recovery material is escrowed and accessible to authorised recovery staff before resuming protection. Never publish recovery keys or unredacted device identifiers.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
