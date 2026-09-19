# Quote Readiness Model

The workflow uses a status-first approach rather than relying only on a numerical lead score.

## Statuses

### Q0 — Insufficient RFQ
The RFQ lacks basic information required for meaningful evaluation.

Typical causes:
- Product unclear
- Quantity unknown
- Very little usable requirement information

### Q1 — Clarification Required
The buyer has provided enough information to understand the opportunity, but one or more critical requirements remain unclear.

Typical causes:
- AI/transcription scope unclear
- Recording requirements incomplete
- App/cloud requirements unclear
- OEM/ODM customization scope incomplete
- Other technical blockers that affect feasibility, cost, compliance, or lead time

### Q2 — Ready for Internal Review
Customer-facing requirements are sufficiently defined and the RFQ can be routed internally for engineering, procurement, compliance, or costing review.

### Q3 — Ready to Quote
Technical and commercial review has been completed and the opportunity is ready for formal quotation.

## Hard Blocker Logic

A missing field does not automatically block an RFQ. The workflow distinguishes among:

- `known`
- `unknown`
- `not_required`

A blocker is triggered when an unknown requirement materially affects feasibility, cost, compliance, or lead time.

## AI Voice Recorder V1 Requirement Set

| Code | Requirement | Typical Impact |
|---|---|---|
| AR01 | Product Form / Reference Model | Product definition |
| AR02 | Recording Requirement | Feasibility / performance |
| AR03 | Microphone Configuration | Hardware / BOM |
| AR04 | Storage Capacity | BOM |
| AR05 | Battery / Runtime | BOM / compliance / size |
| AR06 | Charging Interface | Hardware / usability |
| AR07 | Bluetooth / Wi-Fi | Chipset / certification |
| AR08 | AI / Transcription Functions | Software / NRE / architecture |
| AR09 | App / Cloud Requirement | Software / backend / privacy |
| AR10 | Language Requirements | AI / UX / scope |
| AR11 | OEM / ODM Customization Scope | Engineering / tooling / packaging |
| AR12 | Quantity | Commercial viability / costing |

## Reliability Rule

The LLM may occasionally return labels such as `Clarification Required` or `Q1 - Clarification Required`. A JavaScript normalization step converts supported variations into the stable routing values `Q0`, `Q1`, `Q2`, or `Q3` before the Switch node.
