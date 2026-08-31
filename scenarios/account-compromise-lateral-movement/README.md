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

Completion Criteria
- Suspicious behavior is visible in Splunk.
- A correlation rule identifies the behavior.
- Shuffle enriches available indicators.
- The response follows the defined risk policy.
