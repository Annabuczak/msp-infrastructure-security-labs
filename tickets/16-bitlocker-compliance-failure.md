# INC-016 | BitLocker compliance failure

[All scenarios](../README.md#scenario-index)

**Technology:** Intune / Entra / BitLocker

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

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

## Simulated root cause

Protection suspended after firmware maintenance.

## Proposed resolution

Confirm recovery key escrow, resume protection using approved procedure and sync Intune.

## Verification plan

Verify protection, compliance and authorised access.

## Skills covered

TPM, encryption, endpoint compliance

## Diagnostic interpretation and escalation

Distinguish encryption percentage from protection status: a fully encrypted volume may have protection suspended. Verify the specific Intune compliance failure and policy assignment rather than assuming suspension explains it. Confirm recovery material is escrowed and accessible to authorised recovery staff before resuming protection. Never publish recovery keys or unredacted device identifiers.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
