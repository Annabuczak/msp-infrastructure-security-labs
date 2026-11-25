# MSP-012: Live Discover query returns no results

> **Fictional training simulation — not executed.** All symptoms, timelines and example observations below are invented teaching inputs. No client incident, measured outcome or professional achievement is claimed.

[Ticket index](../README.md) · [Environment](../docs/lab-environment.md) · [Evidence policy](../docs/evidence-policy.md)

## Scenario and impact

A fictional analyst cannot find expected endpoint activity.

**Area:** Sophos XDR. Assess priority from scope, urgency and security impact; no real SLA is implied.

## Competing explanations

Wrong data source or time range; ingestion delay; offline device; collection disabled; incorrect query/schema.

## Investigation procedure

1. Record the query, source, time range, device selection and completion status. Separate an empty result from a failed query.
2. Check entitlement, role, device availability and collection configuration. Endpoint and Data Lake queries answer different questions.
3. Run a small known-good query against an available device or known collected event. Validate the current schema before adapting SQL.

## Diagnostic examples

Examples are unexecuted. Confirm [prerequisites and command limits](../docs/command-reference.md) and substitute authorised lab targets first.

```sql
-- Illustrative Live Discover endpoint query, not Data Lake SQL.
-- Validate the processes table in the tenant query editor first.
SELECT pid, name, path
FROM processes
WHERE name LIKE '%powershell%'
LIMIT 50;
```

**Simulated evidence and interpretation:** Invented test: a historical search uses a time window that ends before the activity. The process query above only illustrates current process inspection; it cannot prove past execution.

## Root-cause reasoning

An incorrect time range is the scenario cause, conditional on collection and successful query execution. Zero results do not establish a clean endpoint.

**Confidence:** unverified outside this fictional scenario. Genuine results would need their own dated evidence record.

## Proposed remediation and rollback

Correct the search window/source and document coverage gaps. Any collection-policy change needs the owner's approval and a recorded previous setting.

## Validation and closure criteria

Recover a known event and record remaining gaps, query status and timestamps. Avoid claiming comprehensive historical coverage.

**Actual outcome:** not tested. These criteria describe what would be checked; they do not report a successful fix.

## Escalation

Escalate missing telemetry during an incident to the detection owner. Provide scope, UTC timeline, versions, checks already attempted, remaining hypotheses and sanitised evidence.

## References

Vendor references checked on 25 November 2026. They support product or command details, not the fictional outcome. Confirm the exact deployed version and tenant capabilities.

- [Sophos Live Discover](https://docs.sophos.com/central/customer/help/en-us/ManageYourProducts/ThreatAnalysisCenter/LiveDiscover/index.html)
