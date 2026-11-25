# INC-019 | Email held by impersonation protection

[All tickets](../README.md#ticket-index)

**Technology:** Mimecast / Exchange

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

## Incident description

Expected supplier email held.

## Investigation

Track message, review triggered policy, SPF/DKIM/DMARC, sender and Reply-To, phishing indicators; independently validate supplier.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Resolve-DnsName -Type TXT example.com
Resolve-DnsName -Type TXT _dmarc.example.com
Resolve-DnsName -Type TXT selector._domainkey.example.com
```

## Root cause assessment

Reply-To mismatch and financial language trigger policy.

## Response procedure

Release only after validation; seek narrow approved policy changes for repeated cases. Authentication passes alone do not prove safety.

## Verification checks

Confirm delivery and ongoing phishing protection.

## Skills covered

Email authentication, phishing triage

## Additional diagnostic guidance

Review the actual message headers and triggered policy, not only current DNS. Obtain the DKIM selector and signing domain from the message; the selector shown is a placeholder, and DNS may involve CNAME delegation. Authentication passes do not establish benign content. Validate requests through a known supplier channel and prefer a single-message release over a broad sender bypass.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
