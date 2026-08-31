# C2 Communication Detection and Automated Containment

## Objective

Detect simulated command-and-control communication, enrich the destination IOC, determine risk, and perform a safe automated response.

## Data Sources

- Suricata alerts
- Network connection metadata
- Splunk indexed events

## Expected Flow

```text
Simulated C2 Activity → Suricata → Splunk Detection → Shuffle
→ IOC Extraction → Enrichment → Risk Decision
→ Discord / TheHive / Temporary Firewall Block
```

Completion Criteria
- A Suricata alert is ingested by Splunk.
- Splunk triggers the C2 detection.
- Shuffle extracts the destination IP or domain.
- The IOC receives enrichment.
- The workflow applies the response policy.
