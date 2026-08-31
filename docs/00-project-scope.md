# Project Scope

## Purpose

The purpose of this project is to build a local SOAR lab that detects selected security events in Splunk and automates enrichment, triage, alerting, and limited containment actions through Shuffle.

## In Scope

- Local collection and analysis of security telemetry in Splunk
- Suricata network alerts
- Splunk detection and correlation searches
- Shuffle automation workflows
- IOC extraction and enrichment
- VirusTotal reputation lookup, when an API key and Internet access are available
- Discord notifications
- Optional TheHive case creation
- Safe containment simulations in the local lab
- Documentation and test evidence for every scenario

## Out of Scope

- Production deployment
- Enterprise-scale high availability
- Full EDR deployment
- Real malware execution
- Attacks against non-lab systems
- Permanent blocking of public IP addresses
- Automated response without defined risk thresholds
- Storage of secrets in this repository

## Success Criteria

A scenario is considered complete when:

1. A simulated event generates usable telemetry.
2. Splunk detects or correlates the event.
3. A workflow is triggered in Shuffle.
4. Relevant indicators or context are enriched.
5. A documented risk decision is made.
6. The expected notification, case, or containment action is performed.
7. Test evidence is captured and sanitized.

## Implementation Order

1. C2 Communication Detection and Automated Containment
2. Malware Behavior Detection and Automated Response
3. Account Compromise and Lateral Movement Detection
