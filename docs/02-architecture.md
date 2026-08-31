# Solution Architecture

## Design Principle

The lab uses a local-first architecture. Security telemetry is generated and processed inside the existing virtual environment. External services are used only as optional API integrations for IOC enrichment and notifications.

## Components

| Component | Responsibility |
|---|---|
| Suricata | Detect suspicious network activity and generate alerts |
| Splunk | Ingest telemetry, run detections, correlate events, and trigger automation |
| Shuffle | Extract data, enrich indicators, calculate risk, and execute response actions |
| VirusTotal | Provide optional reputation information for IPs, domains, URLs, and hashes |
| TheHive | Create and track incident cases |
| Discord | Send analyst notifications |
| Firewall | Apply controlled, temporary blocking in the lab when authorized |

## Architecture Flow

```text
[Simulated Activity]
        ↓
[Suricata / Endpoint Logs / Authentication Logs]
        ↓
[Splunk Indexing and Normalization]
        ↓
[Detection Rule or Correlation Search]
        ↓
[Webhook / Alert to Shuffle]
        ↓
[IOC Extraction and Context Enrichment]
        ↓
[Risk Scoring and Decision]
        ↓
 ┌──────────────────────────────────────────────┐
 │ Low Risk: Discord notification / monitoring  │
 │ Medium Risk: TheHive case / analyst review   │
 │ High Risk: Temporary containment + case      │
 └──────────────────────────────────────────────┘
```

| Source | Destination | Purpose | Protocol / Port |
|---|---|---|---|
| Suricata | Splunk | Alert ingestion | TODO |
| Splunk | Shuffle | Workflow trigger | HTTPS / Webhook |
| Shuffle | VirusTotal | IOC lookup | HTTPS |
| Shuffle | Discord | Notification | HTTPS |
| Shuffle | TheHive | Case creation | HTTPS |
| Shuffle | Firewall | Temporary block action | TODO |

## Security Requirements
- Use HTTPS for API communications whenever supported.
- Store all credentials outside version control.
- Validate and sanitize IOC fields before using them in firewall commands.
- Maintain an allowlist for internal infrastructure and trusted services.
- Record every automated response action in Splunk and/or TheHive.

