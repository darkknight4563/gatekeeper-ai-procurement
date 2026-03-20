# /procurement:evaluate

Run a complete procurement evaluation workflow on vendor proposals in the current working folder.

## Steps

1. Identify all vendor proposal documents (PDF, DOCX, TXT) in the working folder
2. Ask the user for:
   - Procurement category (e.g., subsea_systems, drilling_equipment, marine_logistics)
   - Whether specific RFP requirements should be checked
   - Custom evaluation weights (or use defaults: 30% technical, 25% price, 15% delivery, 10% HSE, 10% experience, 10% commercial)
3. For each proposal:
   - Extract text from the document
   - Call `gatekeeper_analyze_proposal` with vendor name, content, and category
   - Call `gatekeeper_extract_pricing` for detailed pricing data
4. If RFP requirements provided:
   - Call `gatekeeper_compliance_check` for each vendor
5. Call `gatekeeper_risk_assessment` for each vendor
6. Call `gatekeeper_compare_bids` with all vendor summaries
7. Call `gatekeeper_visualization_dashboard` to generate chart data
8. Render interactive visual dashboard inline (radar charts, pricing bars, compliance heatmap, risk matrix, executive scorecard)
9. Call `gatekeeper_generate_report` with all aggregated data
10. Save the report as PDF to the working folder

## Output

- Interactive visual dashboard rendered inline in the conversation
- Professional procurement evaluation report saved as PDF
- Summary with recommendation, rankings, and critical action items
