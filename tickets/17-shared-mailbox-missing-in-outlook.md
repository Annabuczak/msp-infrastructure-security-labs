# INC-017 | Shared mailbox missing in Outlook

[All scenarios](../README.md#scenario-index)

**Technology:** Exchange Online

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Newly assigned shared mailbox not visible.

## Investigation

Verify mailbox, delegation, Full Access vs Send As/On Behalf, web access, group membership and automapping.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Connect-ExchangeOnline
Get-MailboxPermission -Identity shared@example.com
Get-RecipientPermission -Identity shared@example.com
```

## Simulated root cause

Group-based Full Access does not automap.

## Proposed resolution

Confirm approved permissions and manually add mailbox as necessary.

## Verification plan

Verify authorised mailbox actions only.

## Skills covered

Exchange delegation, Outlook

## Diagnostic interpretation and escalation

Full Access, Send As and Send on Behalf are distinct rights. Group-based Full Access does not provide automatic mailbox mapping. Confirm access through a supported web/client method before treating lack of automatic display as missing permissions. Use the add-mailbox workflow appropriate to Classic Outlook, New Outlook or Outlook on the web.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
