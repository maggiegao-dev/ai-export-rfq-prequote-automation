# Architecture

## V1 Scope

The V1 automates the pre-quote stage for overseas RFQs received by a consumer electronics OEM/ODM manufacturer.

```text
RFQ Form
  ↓
AI RFQ Analyzer
  ↓
JSON Parse + Status Normalization
  ↓
Quote Readiness Switch
  ↓
Q1 Clarification Email Draft
  ↓
Save RFQ Record
  ↓
Wait
  ↓
Follow-up Reminder Payload
```

## Components

### 1. RFQ Intake
A lightweight form captures buyer identity, market, product category, and unstructured RFQ text.

### 2. AI RFQ Analyzer
The model extracts structured requirements and evaluates whether the RFQ is sufficiently defined for quotation.

### 3. JSON Normalization
A JavaScript Code node parses the model response and normalizes quote-readiness labels into stable values: `Q0`, `Q1`, `Q2`, `Q3`.

### 4. Routing
An n8n Switch node routes the opportunity according to quote-readiness status.

### 5. Clarification Draft
For Q1 opportunities, a second AI step drafts a concise B2B clarification email based on missing information and hard blockers.

### 6. Persistence
The workflow writes buyer, product, readiness, blocker, missing-information, action, summary, and email-draft data into an n8n Data Table.

### 7. Follow-up Reminder
A Wait node is used in the demo path, followed by a Code node that creates a reminder payload. In a production implementation this can be connected to Gmail, Slack, CRM, Calendar, or another notification channel.

## Design Principle

The workflow does **not** automatically quote. Its role is to determine whether an RFQ is quote-ready and reduce manual pre-quote coordination.

## Security Notes

- API credentials must stay inside n8n credentials and must not be committed to GitHub.
- Production URLs should not be exposed in public documentation unless intentionally used as a public demo.
- Workflow exports should be reviewed before publication to remove sensitive IDs, credentials, URLs, and customer data.
