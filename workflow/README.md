# Workflow Export

The production workflow is implemented in n8n Cloud.

## Current Node Sequence

```text
On form submission
→ Message a model (RFQ Analyzer)
→ Code in JavaScript (parse + normalize)
→ Switch (Q0 / Q1 / Q2 / Q3)
→ Message a model (Clarification Email Draft, Q1 path)
→ Insert row (n8n Data Table)
→ Wait
→ Code in JavaScript (Follow-up Reminder Payload)
```

## Before Publishing an n8n JSON Export

Review the export and remove or replace any sensitive information, including:

- Credential references
- Production form URLs
- Workspace IDs
- Internal table IDs
- Personal email addresses
- Real customer data
- API keys or tokens

Never commit live credentials to a public repository.

## Planned File

A credential-safe export can later be added here as:

```text
workflow/ai-export-rfq-prequote-v1.json
```
