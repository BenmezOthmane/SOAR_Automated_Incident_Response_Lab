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
