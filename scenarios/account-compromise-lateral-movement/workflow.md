# Shuffle Workflow

## Trigger

- Source: Splunk alert or webhook
- Required fields: TODO

## Workflow Steps

1. Validate input fields.
2. Extract IOC, user, host, and event context.
3. Check local allowlists.
4. Enrich IOC or context.
5. Calculate risk.
6. Apply response policy.
7. Record workflow outcome.
8. Send notification and/or create case.

## Required Integrations

- Splunk
- Shuffle
- Discord
- VirusTotal, optional
- TheHive, optional
- Firewall action, optional

## Failure Handling

- If enrichment fails, continue with a reduced-confidence decision.
- If a containment action fails, notify the analyst and record the failure.
