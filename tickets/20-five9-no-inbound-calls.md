# MSP-020: Agent is signed in but receives no inbound calls

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

One fictional agent receives no queued work while peers do.

**Area:** Five9. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Not-ready state; missing skill/campaign assignment; station disconnected; routing rules; insufficient eligible call demand.

## Investigation procedure

1. Confirm the affected channel, agent state, station connection and time window. A successful web login does not mean the agent is eligible for routing.
2. Have a supervisor inspect the relevant campaign/skill assignments, schedule and routing configuration. Compare a genuinely equivalent agent.
3. Arrange a controlled test interaction through the intended route. Preserve state history and call-routing information without exposing caller details.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```powershell
# Optional connectivity check only; this cannot validate queue eligibility.
$Five9WebHost = 'tenant-web.lab.example'
Test-NetConnection $Five9WebHost -Port 443
```

**Simulated evidence and interpretation:** Fictional supervisor view: agent is ready and station is connected, but the required skill is absent. No actual queue statistics are claimed.

## Root-cause reasoning

Missing approved routing assignment is the scenario cause only if the test interaction is eligible for that skill and other routing criteria.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Have the supervisor apply the authorised assignment and record the previous value. Avoid changing global routing to fix one agent.

## Validation and closure criteria

Verify the controlled interaction reaches the agent, audio works and unrelated queues remain unaffected.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate unexplained routing decisions with sanitised test-call ID, UTC time and state history. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Five9 technical requirements](https://documentation.five9.com/bundle/technical-reqs/page/technical-reqs/landing-technical-reqs.htm)
