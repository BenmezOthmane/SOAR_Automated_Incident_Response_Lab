# Incident Response Runbook

## Alert Name

TODO

## Analyst Validation

- Verify the source event.
- Confirm the IOC is not allowlisted.
- Review related Splunk events.
- Confirm the affected asset is a lab system.

## Response by Risk Level

### Low Risk

- Notify via Discord.
- Monitor for recurrence.

### Medium Risk

- Create a case.
- Request analyst review.

### High Risk

- Create or update a case.
- Notify analysts.
- Apply approved temporary containment.
- Validate that the containment action succeeded.

## Closure Criteria

- Event reviewed.
- Response action documented.
- Any temporary containment reverted when appropriate.
- Evidence saved in the repository after sanitization.
