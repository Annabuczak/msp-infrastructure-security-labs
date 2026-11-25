# INC-020 | Wi-Fi connected but no internet

[All scenarios](../README.md#scenario-index)

**Technology:** Windows / DHCP / DNS

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Laptop connects to Wi-Fi after ISP equipment replacement but cannot browse.

## Investigation

Test hotspot, IP configuration, gateway, DHCP, DNS, routes and saved profile; compare working device.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```powershell
ipconfig /all
netsh wlan show interfaces
netsh wlan show profiles
Get-NetIPConfiguration
route print
nslookup example.com
Test-NetConnection example.com -Port 443
# After approved DHCP configuration:
ipconfig /release
ipconfig /renew
ipconfig /flushdns
```

## Simulated root cause

Outdated static configuration.

## Proposed resolution

Confirm approved settings, restore DHCP if appropriate, reconnect and renew lease.

## Verification plan

Verify address, gateway, DNS and internet/corporate access.

## Skills covered

TCP/IP, wireless troubleshooting

## Diagnostic interpretation and escalation

Record the original IP, prefix, gateway and DNS configuration before changing it. Confirm whether static addressing is intentional. DHCP release/renew is disruptive and can disconnect remote support; arrange a recovery route and target the affected adapter. Test DNS and the required applications separately; flushing DNS does not repair an incorrect gateway.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
