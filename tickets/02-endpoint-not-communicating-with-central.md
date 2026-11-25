# INC-002 | Endpoint not communicating with Central

[All tickets](../README.md#ticket-index)

**Technology:** Sophos Central

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

Endpoint appears offline while connected.

## Investigation

Check last contact, services, DNS, proxy, HTTPS and diagnostic logs.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
Get-Service *Sophos*
ipconfig /all
Test-NetConnection -ComputerName 'required-sophos-hostname.example' -Port 443
Resolve-DnsName 'required-sophos-hostname.example'
```

## Root cause assessment

Proxy blocks required cloud services.

## Response procedure

Correct approved proxy configuration; restart components only per supported procedures.

## Verification checks

Confirm online status, policy updates and healthy protection.

## Skills covered

Windows services, DNS, proxy

## Additional diagnostic guidance

Use the required Sophos destinations for the tenant region and installed product. A TCP 443 success does not demonstrate TLS, proxy authentication or cloud registration success. Check system time and certificate errors, and distinguish an offline device from a stale console record. Keep tamper protection enabled.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
