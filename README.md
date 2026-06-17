# Jira Monte Carlo Forecasting Playbook

Velocity forecasts fail because they assume a perfectly steady team and treat statistical averages as guarantees. This repository provides the technical workflows, gadget benchmarks, and execution steps to replace subjective story point estimation with throughput-based Monte Carlo simulations in Jira.

By modeling 10,000 probabilistic futures, you can shift from guessing delivery dates to committing with 85% mathematical confidence. Last updated: June 2026.

## What's in this repo

* [Why Velocity Fails & The Throughput Advantage](https://www.google.com/search?q=%23why-velocity-fails--the-throughput-advantage)
* [The 4 Flow Metrics (Actionable Agile)](https://www.google.com/search?q=%23the-4-flow-metrics-actionable-agile)
* [The 6-Step Jira Execution Plan](https://www.google.com/search?q=%23the-6-step-jira-execution-plan)
* [Reading the S-Curve & The 85% Rule](https://www.google.com/search?q=%23reading-the-s-curve--the-85-rule)
* [Jira Tooling: Actionable Agile vs. Broken Build](https://www.google.com/search?q=%23jira-tooling-actionable-agile-vs-broken-build)
* [Quick Reference Assets](https://www.google.com/search?q=%23quick-reference-assets)
* [Sources & Deeper Reading](https://www.google.com/search?q=%23sources--deeper-reading)

---

## Why Velocity Fails & The Throughput Advantage

Velocity forecasting requires humans to guess the size of tasks using abstract story points, and then averages those guesses to predict the future. Because an average represents the 50th percentile, planning a release around your average velocity mathematically guarantees a 50% failure rate.

Monte Carlo forecasting ignores story points entirely. Instead, it uses throughput—the exact raw count of items your team moves to "Done" over a specific timeframe. By ensuring backlog items are broken down to roughly similar sizes, you can run thousands of simulations on this historical throughput to generate highly accurate forecasts without ever holding an estimation session.

**Full breakdown:** [Why Velocity Forecasts Fail (and Monte Carlo Wins)](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/agile-forecasting-noestimates.html)

---

## The 4 Flow Metrics (Actionable Agile)

Built upon the methodologies of flow pioneer Daniel Vacanti, the Actionable Agile method relies strictly on empirical data. The predictive engine is powered exclusively by four objective system metrics:

* **Work In Progress (WIP):** The total number of items actively being worked on.
* **Cycle Time:** The total elapsed time for an item to move from an active state to a closed state.
* **Throughput:** The exact count of work items finished per designated time period.
* **Work Item Age:** The time elapsed since an active item entered your workflow.

These metrics feed two distinct models: A "When" forecast predicts the completion date for a fixed scope, while a "How Many" forecast predicts the total backlog items you can finish by a fixed calendar date.

**Full breakdown:** [Actionable Agile Monte Carlo, Explained Simply](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/actionable-agile-monte-carlo-explained.html)

---

## The 6-Step Jira Execution Plan

Jira lacks a native Monte Carlo engine, meaning a third-party app is required to sample the historical data. To generate a reliable forecast, you must feed the algorithm a minimum of 15 to 20 historically completed items. Fewer data points result in an erratic and mathematically unreliable distribution.

1. **Install a Gadget:** Add a verified forecasting gadget to your Jira dashboard.
2. **Define the Window:** Point the simulation to a JQL filter reflecting the last 30 to 60 days of completed work.
3. **Scope Remaining Work:** Provide the precise count of unstarted and in-progress items remaining in your target backlog or epic.
4. **Set Trial Count:** Configure the gadget to execute 10,000 randomized simulation runs.
5. **Execute:** Run the simulation to generate a cumulative probability curve.
6. **Extract:** Locate the date associated with the 85th percentile confidence level to communicate to stakeholders.

**Full breakdown:** [Run a Monte Carlo Forecast in Jira in 6 Steps](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-run-monte-carlo-simulation-in-jira.html)

---

## Reading the S-Curve & The 85% Rule

Generating the chart is useless if you misinterpret the data. The chart outputs a cumulative probability line (the S-curve) overlaid on a histogram.

Many teams mistakenly target the middle of the chart (the 50th percentile) as their delivery date. Committing to the 50% date is a literal coin toss that leaves absolutely no buffer for technical debt or team sickness. You must always anchor commitments to the 85th or 95th percentiles to ensure a high probability of success.

The shape of the distribution also reveals workflow health. A narrow distribution indicates stable, predictable throughput, whereas a wide distribution warns that the team's delivery is erratic and highly sensitive to underlying flow issues.

**Full breakdown:** [Your Monte Carlo Chart Is Useless If You Misread It](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-read-monte-carlo-forecast-chart.html)

---

## Jira Tooling: Actionable Agile vs. Broken Build

To execute the 10,000 randomized probability trials natively in Jira, you must use a specialized marketplace app.

Actionable Agile (by 55Degrees) is universally recognized as the industry standard for academic accuracy. It excels in deep data analysis, outlier filtering, and full flow metrics suites (including aging WIP and cycle time scatterplots).

Broken Build is a highly competitive, budget-friendly alternative. It focuses on lightweight, user-friendly dashboard simplicity that makes 50%, 85%, and 95% percentile lines easy for non-technical leadership to digest directly inside Jira. Both tools support epic-level forecasting by filtering via JQL or Epic Links.

**Full breakdown:** [The Best Monte Carlo Jira Gadgets](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/monte-carlo-simulation-chart-gadget-jira.html)

---

## Quick Reference Assets

* [`data/jira-gadget-comparison.csv`](https://www.google.com/search?q=data/jira-gadget-comparison.csv) — Feature, pricing structure, and metric capability breakdown of Jira forecasting tools.
* [`6-step-jira-execution.md`](https://www.google.com/search?q=6-step-jira-execution.md) — A copy-pasteable checklist for configuring the JQL, trial runs, and sample scoping for Jira dashboards.
* [`CHEATSHEET.md`](https://www.google.com/search?q=CHEATSHEET.md) — 1-page reference guide for explaining percentiles, the S-Curve, and Vacanti's four flow metrics to non-technical stakeholders.

---

## Sources & Deeper Reading

* [Actionable Agile Monte Carlo, Explained Simply](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/actionable-agile-monte-carlo-explained.html)
* [Why Velocity Forecasts Fail (and Monte Carlo Wins)](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/agile-forecasting-noestimates.html)
* [Forecast Release Dates With 85% Confidence](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/forecasting-release-dates-with-monte-carlo.html)
* [Your Monte Carlo Chart Is Useless If You Misread It](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-read-monte-carlo-forecast-chart.html)
* [Run a Monte Carlo Forecast in Jira in 6 Steps](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-run-monte-carlo-simulation-in-jira.html)
* [The Best Monte Carlo Jira Gadgets](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/monte-carlo-simulation-chart-gadget-jira.html)
* [Scrum Monte Carlo Forecasting in Jira, Step by Step](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/scrum-monte-carlo-forecasting-in-jira.html)

---

## Contributing / Corrections

App features on the Atlassian Marketplace evolve rapidly. If you spot a change in the way Actionable Agile or Broken Build handles JQL filtering or dataset caps, please open an Issue or submit a PR.

---

**About the Author**

I’m Ayush Bisht, a Content Engineer and AI tools specialist passionate about building smart, scalable, and engaging digital experiences. Currently working with AgileWow, I blend content strategy with AI-driven workflows to create efficient, impactful solutions.

[LinkedIn](https://www.linkedin.com/in/ayush-bisht-92abb1315/).
