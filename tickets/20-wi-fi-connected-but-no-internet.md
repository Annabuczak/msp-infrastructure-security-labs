# INC-020 | Wi-Fi connected but no internet

[All tickets](../README.md#ticket-index)

**Technology:** Windows / DHCP / DNS

**Priority:** P3 · **Support level:** Tier 1

**Case type:** Anonymised workplace case.

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

## Root cause assessment

Outdated static configuration.

## Response procedure

Confirm approved settings, restore DHCP if appropriate, reconnect and renew lease.

## Verification checks

Verify address, gateway, DNS and internet/corporate access.

## Skills covered

TCP/IP, wireless troubleshooting

## Additional diagnostic guidance

Record the original IP, prefix, gateway and DNS configuration before changing it. Confirm whether static addressing is intentional. DHCP release/renew is disruptive and can disconnect remote support; arrange a recovery route and target the affected adapter. Test DNS and the required applications separately; flushing DNS does not repair an incorrect gateway.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
