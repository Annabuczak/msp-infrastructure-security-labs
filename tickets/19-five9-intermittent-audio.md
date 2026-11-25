# MSP-019: Five9 calls have intermittent audio gaps

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional remote agent reports broken speech during busy periods.

**Area:** Five9. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Wi-Fi contention; upstream saturation; packet loss/jitter; endpoint resource pressure; headset problem; provider path issue.

## Investigation procedure

1. Record call examples, timing, network path, VPN state and whether the problem affects one or both directions.
2. Use the approved voice-quality assessment and media statistics. Compare an authorised wired test and a known-good headset while controlling other variables.
3. Correlate gaps with Wi-Fi conditions, endpoint load and competing traffic. A fast speed-test result does not rule out burst loss or jitter.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
Get-NetAdapterStatistics
Get-Process | Sort-Object CPU -Descending |
    Select-Object -First 10 ProcessName,Id,CPU,WorkingSet64
netsh wlan show interfaces
```

**Simulated evidence and interpretation:** Fictional comparison: audio gaps coincide with a large upload and improve when the upload is paused. CPU shown here is cumulative process time, not instantaneous utilisation.

## Root-cause reasoning

Uplink contention is the proposed explanation; controlled repetition and media statistics are needed to separate it from Wi-Fi or provider issues.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Reschedule nonessential traffic or apply approved traffic management. Test one change at a time; save previous settings and avoid bypassing corporate VPN policy.

## Validation and closure criteria

Repeat representative calls during the original problem period and record voice metrics against the deployment requirements.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate persistent loss/jitter with timestamps, network comparison and vendor assessment results. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Five9 network and deployment requirements](https://documentation.five9.com/bundle/technical-reqs/page/technical-reqs/landing-technical-reqs.htm)
- [Five9 technical requirements guide](https://documentation-be.five9.com/bundle/five9-technical-requirements/raw/resource/enus/five9-technical-requirements.pdf)
