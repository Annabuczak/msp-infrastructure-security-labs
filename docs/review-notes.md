# Review notes

Prepared on 25 November 2026 as a new collection requested by the portfolio owner. These are not revisions of a supplied 20-ticket repository: that source was unavailable, and the owner requested new fictional scenarios.

## Technical review decisions

- DNS resolution, transport reachability and application health are treated separately.
- APIPA does not identify which DHCP component failed.
- Account lockout investigation includes recurring credential sources and security escalation.
- Share and NTFS permissions are evaluated together with authorisation.
- FortiGate diagnostics are filtered and bounded, with cleanup and hardware-offload limitations.
- An established IPsec tunnel does not prove working routes or return traffic.
- Guest isolation is tested with known listening services; failed ping is not conclusive.
- Sophos connectivity, effective policy, telemetry, threat triage and response are separate cases.
- Live Discover source/schema and coverage are explicit; no-result queries are not clean bills of health.
- Containment, investigation and recovery are distinct incident-response stages.
- Five9 scenarios separate authentication, installed components, media, call quality and routing eligibility.
- Version-dependent Five9 requirements are referenced instead of inventing universal ports or thresholds.

## Validation limits

The collection has been checked for ticket count, required sections and local Markdown links. Vendor documentation informed product-specific examples. No Windows domain, FortiGate, Sophos tenant or Five9 deployment was available for execution. Product behaviour, permissions and syntax must be confirmed in the actual lab. Existing public repositories and their screenshots have not received a full technical, provenance or secret-history audit.

## Publication status

Approved for publication by the portfolio owner on 25 November 2026. All 20 tickets remain fictional, unexecuted simulations. Add real lab evidence separately as work is performed.
