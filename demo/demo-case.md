# Demo Case — AI Voice Recorder RFQ

## Buyer Input

**Buyer:** Sofia Lindberg  
**Company:** Nordic Vision AB  
**Market:** Sweden / EU  
**Product:** AI Voice Recorder

### RFQ

```text
We are looking for 6,000 AI voice recorders for Sweden and the EU market.

Requirements:
- 64GB storage
- Bluetooth
- AI transcription
- Custom logo
- CE and RoHS required
- Target price below USD 33
- Delivery required in February

We have not yet confirmed the transcription languages, whether transcription should run on-device or in the cloud, the required recording specifications, battery runtime, or whether a branded mobile app is required.

Please advise what additional information you need before preparing a quotation.
```

## Expected AI Interpretation

Known information includes:

- Quantity: 6,000 units
- Storage: 64GB
- Bluetooth required
- AI transcription requested
- Custom logo required
- CE / RoHS required
- Target price: below USD 33
- Delivery: February

Critical unknowns include:

- On-device vs cloud transcription
- Required transcription languages
- Recording specifications
- Battery/runtime target
- Branded mobile app requirement

## Quote Readiness

**Q1 — Clarification Required**

The RFQ is commercially meaningful, but technical scope is not sufficiently defined to proceed directly to formal quotation.

## Automated Actions

The workflow:

1. Extracts buyer and product data.
2. Detects missing critical specifications.
3. Assigns the RFQ to Q1.
4. Generates clarification questions.
5. Drafts a professional English clarification email.
6. Saves the RFQ and AI analysis to an n8n Data Table.
7. Waits for the configured demo interval.
8. Generates a follow-up reminder payload.

## Example Clarification Topics

The buyer is asked to confirm:

- Whether transcription should be processed on-device or in the cloud
- Required transcription languages
- Recording format and quality requirements
- Battery runtime expectations
- App/cloud requirements
- Final delivery timing and relevant commercial details

## Validation Result

The Production workflow was tested end-to-end in n8n Cloud and successfully executed the Q1 path through record insertion, wait, and follow-up reminder generation.
