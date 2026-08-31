# SOAR Automated Incident Response Lab

A local, resource-conscious Security Operations Automation and Response (SOAR) lab designed to simulate realistic incident detection, enrichment, triage, and response workflows.

## Project Objectives

This project demonstrates how a SOC can automate repetitive incident-response tasks while preserving human control over high-impact actions.

The lab focuses on three common enterprise security scenarios:

1. C2 Communication Detection and Automated Containment
2. Malware Behavior Detection and Automated Response
3. Account Compromise and Lateral Movement Detection

## Core Technologies

- Splunk Enterprise: log collection, search, detection, and correlation
- Suricata: network intrusion detection and alert generation
- Shuffle: SOAR workflow automation
- TheHive: case management (optional in the initial phase)
- VirusTotal API: IOC enrichment
- Discord: alert notification
- VMware: local virtualized lab environment

## Lab Constraints

- Available RAM for VMware: approximately 5 GB
- Available storage for the lab: approximately 30 GB
- All core services are deployed locally in the existing lab environment.
- No cloud-hosted replacement of the lab infrastructure is required.

## High-Level Data Flow

```text
Security Event
    ↓
Suricata / Endpoint Telemetry / Authentication Logs
    ↓
Splunk Detection or Correlation Rule
    ↓
Shuffle Workflow
    ↓
IOC or Context Enrichment
    ↓
Risk Decision
    ↓
Notification, Case Creation, or Containment Action
```
## Repository Structure

docs/        Project, environment, architecture, and policy documentation
scenarios/   Scenario-specific detection, workflow, runbook, and test documents
configs/     Sanitized configuration examples
scripts/     Safe simulation and validation scripts
evidence/    Screenshots and sanitized sample logs

## Disclaimer
This project is an educational lab. Automated blocking, account disabling, and endpoint isolation must only be tested against authorized lab systems.

---

### `docs/00-project-scope.md`

```md
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
```
## Implementation Order

1. C2 Communication Detection and Automated Containment
2. Malware Behavior Detection and Automated Response
3. Account Compromise and Lateral Movement Detection
