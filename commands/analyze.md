# /procurement:analyze

Analyze a single vendor proposal document in detail.

## Steps

1. Identify the vendor proposal document (PDF, DOCX, TXT) — if multiple files exist, ask which one
2. Ask the user for vendor name and procurement category
3. Extract text from the document
4. Call `gatekeeper_analyze_proposal` with the content
5. Call `gatekeeper_extract_pricing` for line-item pricing detail
6. Call `gatekeeper_risk_assessment` for risk register
7. Present a structured summary with:
   - Executive summary
   - Pricing breakdown table
   - Delivery schedule
   - Key strengths and weaknesses
   - Risk flags with severity indicators
   - Compliance status (if RFP requirements available)

## Output

- Detailed vendor analysis in the conversation
- Structured data available for later use in bid comparison
