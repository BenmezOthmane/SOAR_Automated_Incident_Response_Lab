# Automated Response Policy

## Purpose

This policy defines how the lab assigns risk and chooses automated actions. The objective is to demonstrate safe SOAR automation while minimizing false-positive impact.

## Risk Levels

| Risk Level | Description | Default Action |
|---|---|---|
| Low | Weak or isolated suspicious signal | Discord notification and monitoring |
| Medium | Suspicious activity supported by enrichment or repeated behavior | Create TheHive case and request analyst review |
| High | Strong evidence of malicious activity or multiple correlated indicators | Create case, notify analysts, and apply approved temporary containment |

## Risk Decision Inputs

A risk decision may consider:

- Suricata alert severity
- Splunk correlation confidence
- VirusTotal reputation, if available
- Number of matching malicious vendors
- IOC recurrence
- Asset criticality
- User privilege level
- Internal allowlist status
- Whether the event is linked to another suspicious event

## Automated Action Rules

### Low Risk

- Send a Discord notification.
- Record the event in Splunk.
- Do not block an IP address.
- Do not disable an account.
- Do not isolate an endpoint.

### Medium Risk

- Send a Discord notification.
- Create a TheHive case when available.
- Attach relevant IOCs and Splunk event details.
- Require analyst approval before containment.

### High Risk

- Send an urgent Discord notification.
- Create or update a TheHive case.
- Apply only pre-approved, reversible containment in the lab.
- Examples: temporary firewall block, disable a test account, or isolate a test endpoint.
- Log the exact response action, timestamp, target, and workflow execution ID.

## Safety Controls

- Never block allowlisted infrastructure.
- Never run destructive commands from unvalidated IOC values.
- Prefer temporary blocks over permanent blocks.
- Use lab-only accounts and endpoints for account disablement or isolation.
- Require manual approval for actions affecting privileged accounts or critical assets.
