# INC-017 | Shared mailbox missing in Outlook

[All tickets](../README.md#ticket-index)

**Technology:** Exchange Online

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Group-based Full Access does not automap.

## Response procedure

Confirm approved permissions and manually add mailbox as necessary.

## Verification checks

Verify authorised mailbox actions only.

## Skills covered

Exchange delegation, Outlook

## Additional diagnostic guidance

Full Access, Send As and Send on Behalf are distinct rights. Group-based Full Access does not provide automatic mailbox mapping. Confirm access through a supported web/client method before treating lack of automatic display as missing permissions. Use the add-mailbox workflow appropriate to Classic Outlook, New Outlook or Outlook on the web.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
