# n8n-error-monitor
Logs n8n workflow failures in Notion, groups repeated errors, and sends Slack alerts for high-severity incidents.

## Setup

1. Import the workflow JSON from this repository into n8n.
2. Connect Notion and Slack in n8n. Follow the [published template guide](https://n8n.io/workflows/16862-route-workflow-error-incidents-to-slack-alerts-with-a-notion-incident-log/) to set up the Notion incident database.
3. In `Set Error Notification Config`, enter your Notion database ID and Slack channel ID. The default minimum severity for Slack alerts is `High`.
4. Open the settings of the workflow you want to monitor and select this monitor as its **Error workflow**.

## Test a repeated failure

Let an automatically triggered test workflow fail the same way twice, one run after the other. The expected result is one Notion incident with `Occurrences` equal to `2`.
