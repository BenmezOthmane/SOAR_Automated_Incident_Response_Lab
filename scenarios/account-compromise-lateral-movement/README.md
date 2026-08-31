# Malware Behavior Detection and Automated Response

## Objective

Detect simulated suspicious execution behavior by correlating endpoint telemetry and network activity.

## Data Sources

- Endpoint process telemetry
- Windows event logs or Sysmon logs
- Suricata alerts or network telemetry
- Splunk indexed events

## Expected Flow

```text
Simulated Suspicious Execution → Endpoint and Network Telemetry
→ Splunk Correlation → Shuffle → IOC Enrichment
→ Risk Decision → Notification / Case / Containment
```

## Completion Criteria
- Authentication and lateral movement events are ingested.
- Splunk correlates the events.
- Shuffle receives account and host context.
- The workflow sends the correct notification or containment action.

