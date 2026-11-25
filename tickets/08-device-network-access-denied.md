# INC-008 | Device network access denied

[All tickets](../README.md#ticket-index)

**Technology:** FortiGate / DHCP / VLANs

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Anonymised workplace case.

## Incident description

New clocking terminal cannot reach management server.

## Investigation

Check physical link, MAC, DHCP, VLAN, access restrictions and traffic logs.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```bash
get system arp
execute dhcp lease-list
show firewall address
show firewall policy
```

## Root cause assessment

Missing authorised MAC entry.

## Response procedure

Verify device identity and obtain approval for scoped access. MAC filtering is spoofable and not strong authentication.

## Verification checks

Confirm correct IP and management server connectivity.

## Skills covered

ARP, DHCP, segmentation

## Additional diagnostic guidance

Identify where access is denied: DHCP admission, switch port or VLAN, a NAC policy, or the firewall. An absent ARP entry is not proof of a MAC restriction. DHCP lease output is relevant only if this FortiGate provides DHCP. Match the endpoint to the actual enforcement rule before changing access; a DHCP reservation is not authentication.

## Evidence status

This case summarises a real workplace incident. Original client logs and screenshots are not published. Additional diagnostic guidance and example commands are reference material; they do not establish which steps were performed or that all verification checks passed.
