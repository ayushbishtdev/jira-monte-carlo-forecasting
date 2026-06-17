# 6-Step Jira Monte Carlo Execution Checklist

Use this configuration guide to properly scope your Jira data and generate an accurate delivery probability chart.

## Prerequisites
- [ ] Ensure your Jira workflow states map correctly to "Done" to capture accurate throughput.
- [ ] Verify you have a minimum of **15 to 20 completed items** in your recent history[cite: 10, 12].

## Execution Steps
1. **Gadget Installation**
   - [ ] Navigate to the Atlassian Marketplace.
   - [ ] Install your chosen forecasting app (e.g., Actionable Agile or Broken Build).
   - [ ] Add the gadget to your active Scrum/Kanban dashboard.
2. **Historical Data Window**
   - [ ] Point the gadget to a specific JQL filter that reflects your *current* team's performance.
   - [ ] Set the lookback window to the last **30 to 60 days**. 
3. **Scope the Target**
   - [ ] Count the exact number of unstarted and in-progress items in your target Release/Epic.
   - [ ] Input this item count into the gadget to serve as the finish line.
4. **Configure Simulation Math**
   - [ ] Ensure the gadget is set to run **10,000 randomized simulation runs** (this smooths the probability curve).
5. **Execute**
   - [ ] Generate the chart. Wait for the histogram and S-curve to render.
6. **Extract the Commitment**
   - [ ] Ignore the 50th percentile marker.
   - [ ] Locate the **85th percentile** date and use this as your baseline release commitment to stakeholders.
