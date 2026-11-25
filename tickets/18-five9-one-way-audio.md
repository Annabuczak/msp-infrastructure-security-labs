# MSP-018: Five9 call connects with one-way audio

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional agent hears the caller but the caller cannot hear the agent.

**Area:** Five9 and FortiGate. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Wrong/muted microphone; privacy permission; device failure; one-way media path; NAT/inspection issue; client defect.

## Investigation procedure

1. Record audio direction, station type, call time and approved test-call identifier. Compare an OS microphone test and the configured application input.
2. Separate browser WebRTC from installed softphone requirements. Review the current tenant/region requirements rather than copying a generic port list.
3. If microphone input works, correlate media diagnostics and firewall traffic in both directions. Inspect NAT and applicable inspection policy; do not infer media health from HTTPS success.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```text
# FortiGate: brief lab capture; review addresses before use.
diagnose sniffer packet any 'host 10.20.10.50 and udp' 4 40 l
```

**Simulated evidence and interpretation:** Fictional evidence: microphone meter works; media leaves the client but return traffic is absent at the observation point. This does not yet identify the dropping device.

## Root-cause reasoning

Media-path failure is a hypothesis. Capture vantage point, offload, transport choice and vendor diagnostics must support a more precise conclusion.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the network owner apply a documented, scoped correction for the actual deployment. Do not globally disable SIP inspection or create unrestricted inbound rules. Keep the prior policy and a tested rollback.

## Validation and closure criteria

Test inbound and outbound calls with two-way audio. Repeat on the original network and check unrelated voice services.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate with call times/IDs, station/client version, direction and sanitised traces; exclude recordings and customer numbers. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Five9 network and deployment requirements](https://documentation.five9.com/bundle/technical-reqs/page/technical-reqs/landing-technical-reqs.htm)
- [Five9 technical requirements guide](https://documentation-be.five9.com/bundle/five9-technical-requirements/raw/resource/enus/five9-technical-requirements.pdf)
