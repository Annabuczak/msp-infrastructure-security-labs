# INC-008 | Device network access denied

[All scenarios](../README.md#scenario-index)

**Technology:** FortiGate / DHCP / VLANs

**Priority:** P3 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

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

## Simulated root cause

Missing authorised MAC entry.

## Proposed resolution

Verify device identity and obtain approval for scoped access. MAC filtering is spoofable and not strong authentication.

## Verification plan

Confirm correct IP and management server connectivity.

## Skills covered

ARP, DHCP, segmentation

## Diagnostic interpretation and escalation

Identify where access is denied: DHCP admission, switch port or VLAN, a NAC policy, or the firewall. An absent ARP entry is not proof of a MAC restriction. DHCP lease output is relevant only if this FortiGate provides DHCP. Match the endpoint to the actual enforcement rule before changing access; a DHCP reservation is not authentication.

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
