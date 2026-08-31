# Lab Environment

## Host System

| Item | Value |
|---|---|
| Host operating system | TODO |
| Total RAM | 12 GB |
| RAM available for VMware | Approximately 5 GB |
| Storage available for the lab | Approximately 30 GB |
| Virtualization platform | VMware |
| Network mode | TODO: NAT / Host-only / Bridged |

## Virtual Machines

| VM Name | Role | Operating System | RAM | vCPU | Disk | IP Address |
|---|---|---|---:|---:|---:|---|
| TODO | Splunk / Suricata / SOAR services | TODO | TODO | TODO | TODO | TODO |
| TODO | Test endpoint or traffic generator | TODO | TODO | TODO | TODO | TODO |

## Local Services

| Service | Role | Version | Deployment Location | Status |
|---|---|---|---|---|
| Splunk Enterprise | SIEM and detection engine | TODO | Local VM | TODO |
| Suricata | Network IDS | TODO | Local VM | TODO |
| Shuffle | SOAR platform | TODO | Local VM | TODO |
| TheHive | Case management | TODO | Local VM / Optional | TODO |
| Discord | Notification channel | N/A | External API integration only | TODO |
| VirusTotal | IOC enrichment | N/A | External API integration only | TODO |

## Resource Strategy

Because the lab has limited resources:

- Core services remain local.
- Only required services should run during testing.
- TheHive may be enabled after initial detection and Shuffle workflows are validated.
- Test traffic and logs should be generated from existing lab systems where possible.
- Large PCAP files, verbose logs, and Docker images should be cleaned up only when no longer needed and after preserving necessary evidence.

## Network Segmentation

| Network / Segment | Purpose | Notes |
|---|---|---|
| Management network | Administrative access to lab services | TODO |
| Test network | Simulated endpoint and attacker activity | TODO |
| Internet access | Optional API enrichment and Discord notifications | TODO |

## Required Secrets

The following values must be stored locally in `.env` and must never be committed:

- `VT_API_KEY`
- `DISCORD_WEBHOOK_URL`
- `SPLUNK_HEC_TOKEN`
- `SHUFFLE_API_KEY`
- `THEHIVE_API_KEY`
- Firewall or platform credentials, if used
