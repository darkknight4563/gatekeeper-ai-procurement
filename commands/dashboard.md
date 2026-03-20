# /procurement:dashboard

Generate an interactive visual procurement dashboard from existing analysis data.

## Steps

1. Check if analysis data exists from previous `gatekeeper_analyze_proposal` or `gatekeeper_compare_bids` calls in this session
2. If no prior analysis exists, ask the user to run `/procurement:evaluate` first or provide the analysis data
3. Call `gatekeeper_visualization_dashboard` requesting all chart types:
   - executive_scorecard
   - radar_scores
   - pricing_comparison
   - delivery_timeline
   - compliance_heatmap
   - risk_matrix
4. Render each visualization as an interactive chart inline:
   - Use Recharts for radar and bar charts
   - Use HTML/CSS for heatmaps and scorecards
   - Use SVG for timeline/Gantt visualizations
   - Apply Gatekeeper AI color scheme: blue (#2563eb) for recommended vendor, amber (#f59e0b) and red (#ef4444) for others
5. Optionally export the dashboard as a styled PDF

## Output

- Full interactive dashboard rendered inline
- Optional PDF export to working folder
