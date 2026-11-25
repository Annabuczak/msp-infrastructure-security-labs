# INC-002 | Endpoint not communicating with Central

[All scenarios](../README.md#scenario-index)

**Technology:** Sophos Central

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

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

## Simulated root cause

Proxy blocks required cloud services.

## Proposed resolution

Correct approved proxy configuration; restart components only per supported procedures.

## Verification plan

Confirm online status, policy updates and healthy protection.

## Skills covered

Windows services, DNS, proxy

## Diagnostic interpretation and escalation

Use the required Sophos destinations for the tenant region and installed product. A TCP 443 success does not demonstrate TLS, proxy authentication or cloud registration success. Check system time and certificate errors, and distinguish an offline device from a stale console record. Keep tamper protection enabled.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
