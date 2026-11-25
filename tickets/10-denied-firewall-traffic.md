# INC-010 | Denied firewall traffic

[All scenarios](../README.md#scenario-index)

**Technology:** FortiGate

**Priority:** P2 · **Support level:** Tier 2

**Case type:** Simulated — not lab-tested or a completed production incident.

## Incident description

Corporate VLAN cannot reach HTTPS application after change.

## Investigation

Identify source, destination, port, interfaces, route, policy order and explicit/implicit deny.

## Diagnostic commands

Illustrative commands only. Replace example addresses and names with authorised targets; check the installed version, permissions and service configuration before use.

```bash
diagnose debug reset
diagnose debug flow filter addr 10.20.30.10
diagnose debug flow show function-name enable
diagnose debug flow trace start 20
diagnose debug enable
# Stop after collecting output:
diagnose debug disable
diagnose debug flow trace stop
diagnose debug reset
```

## Simulated root cause

Source VLAN missing from permitted policy.

## Proposed resolution

Obtain approved narrow policy amendment for required source, destination and service; enable appropriate logging.

## Verification plan

Confirm HTTPS works and unrelated services remain inaccessible.

## Skills covered

Firewall policies, flow diagnostics

## Diagnostic interpretation and escalation

Run in the correct VDOM and coordinate with other administrators before resetting debug settings. Replace the example address with the authorised test source and add destination/protocol/port filters where supported. Capture a bounded reproduction and always stop tracing. Hardware-offloaded sessions may not appear; missing debug output is not proof of no traffic. Do not disable offloading casually.

Reference: [FortiOS 7.4.7 debug flow reference](https://docs.fortinet.com/document/fortigate/7.4.7/cli-reference/159376337/diagnose-debug).

## Evidence status

No execution results or lab evidence are supplied. The root cause above is the scenario assumption; the resolution and verification steps remain proposed.
