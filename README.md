# Jira Monte Carlo Forecasting Playbook

Velocity forecasts fail because they assume a perfectly steady team and treat statistical averages as guarantees[cite: 7]. This repository provides the technical workflows, gadget benchmarks, and execution steps to replace subjective story point estimation with throughput-based Monte Carlo simulations in Jira. 

By modeling 10,000 probabilistic futures, you can shift from guessing delivery dates to committing with 85% mathematical confidence[cite: 8, 10]. Last updated: June 2026.

## What's in this repo

* [Why Velocity Fails & The Throughput Advantage](#why-velocity-fails--the-throughput-advantage)
* [The 4 Flow Metrics (Actionable Agile)](#the-4-flow-metrics-actionable-agile)
* [The 6-Step Jira Execution Plan](#the-6-step-jira-execution-plan)
* [Reading the S-Curve & The 85% Rule](#reading-the-s-curve--the-85-rule)
* [Jira Tooling: Actionable Agile vs. Broken Build](#jira-tooling-actionable-agile-vs-broken-build)
* [Quick Reference Assets](#quick-reference-assets)
* [Sources & Deeper Reading](#sources--deeper-reading)

---

## Why Velocity Fails & The Throughput Advantage

Velocity forecasting requires humans to guess the size of tasks using abstract story points, and then averages those guesses to predict the future[cite: 7]. Because an average represents the 50th percentile, planning a release around your average velocity mathematically guarantees a 50% failure rate[cite: 7]. 

Monte Carlo forecasting ignores story points entirely[cite: 7]. Instead, it uses throughput—the exact raw count of items your team moves to "Done" over a specific timeframe[cite: 7]. By ensuring backlog items are broken down to roughly similar sizes, you can run thousands of simulations on this historical throughput to generate highly accurate forecasts without ever holding an estimation session[cite: 7].

**Full breakdown:** [Why Velocity Forecasts Fail (and Monte Carlo Wins)](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/agile-forecasting-noestimates.html)

---

## The 4 Flow Metrics (Actionable Agile)

Built upon the methodologies of flow pioneer Daniel Vacanti, the Actionable Agile method relies strictly on empirical data[cite: 6]. The predictive engine is powered exclusively by four objective system metrics[cite: 6]:

* **Work In Progress (WIP):** The total number of items actively being worked on[cite: 6].
* **Cycle Time:** The total elapsed time for an item to move from an active state to a closed state[cite: 6].
* **Throughput:** The exact count of work items finished per designated time period[cite: 6].
* **Work Item Age:** The time elapsed since an active item entered your workflow[cite: 6].

These metrics feed two distinct models: A "When" forecast predicts the completion date for a fixed scope, while a "How Many" forecast predicts the total backlog items you can finish by a fixed calendar date[cite: 6].

**Full breakdown:** [Actionable Agile Monte Carlo, Explained Simply](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/actionable-agile-monte-carlo-explained.html)

---

## The 6-Step Jira Execution Plan

Jira lacks a native Monte Carlo engine, meaning a third-party app is required to sample the historical data[cite: 10, 11]. To generate a reliable forecast, you must feed the algorithm a minimum of 15 to 20 historically completed items[cite: 10, 12]. Fewer data points result in an erratic and mathematically unreliable distribution[cite: 10].

1. **Install a Gadget:** Add a verified forecasting gadget to your Jira dashboard[cite: 10].
2. **Define the Window:** Point the simulation to a JQL filter reflecting the last 30 to 60 days of completed work[cite: 10].
3. **Scope Remaining Work:** Provide the precise count of unstarted and in-progress items remaining in your target backlog or epic[cite: 10].
4. **Set Trial Count:** Configure the gadget to execute 10,000 randomized simulation runs[cite: 10].
5. **Execute:** Run the simulation to generate a cumulative probability curve[cite: 10].
6. **Extract:** Locate the date associated with the 85th percentile confidence level to communicate to stakeholders[cite: 10].

**Full breakdown:** [Run a Monte Carlo Forecast in Jira in 6 Steps](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-run-monte-carlo-simulation-in-jira.html)

---

## Reading the S-Curve & The 85% Rule

Generating the chart is useless if you misinterpret the data[cite: 9]. The chart outputs a cumulative probability line (the S-curve) overlaid on a histogram[cite: 9]. 

Many teams mistakenly target the middle of the chart (the 50th percentile) as their delivery date[cite: 9]. Committing to the 50% date is a literal coin toss that leaves absolutely no buffer for technical debt or team sickness[cite: 8, 9]. You must always anchor commitments to the 85th or 95th percentiles to ensure a high probability of success[cite: 9].

The shape of the distribution also reveals workflow health[cite: 9]. A narrow distribution indicates stable, predictable throughput, whereas a wide distribution warns that the team's delivery is erratic and highly sensitive to underlying flow issues[cite: 9].

**Full breakdown:** [Your Monte Carlo Chart Is Useless If You Misread It](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/how-to-read-monte-carlo-forecast-chart.html)

---

## Jira Tooling: Actionable Agile vs. Broken Build

To execute the 10,000 randomized probability trials natively in Jira, you must use a specialized marketplace app[cite: 11]. 

Actionable Agile (by 55Degrees) is universally recognized as the industry standard for academic accuracy[cite: 11]. It excels in deep data analysis, outlier filtering, and full flow metrics suites (including aging WIP and cycle time scatterplots)[cite: 11].

Broken Build is a highly competitive, budget-friendly alternative[cite: 11]. It focuses on lightweight, user-friendly dashboard simplicity that makes 50%, 85%, and 95% percentile lines easy for non-technical leadership to digest directly inside Jira[cite: 11]. Both tools support epic-level forecasting by filtering via JQL or Epic Links[cite: 11].

**Full breakdown:** [The Best Monte Carlo Jira Gadgets](https://scrumdayindia.org/blogs/scrum-monte-carlo-forecasting-in-jira/monte-carlo-simulation-chart-gadget-jira.html)

---

## Quick Reference Assets

* [`data/jira-gadget-comparison.csv`](data/jira-gadget-comparison.csv) — Feature, pricing structure, and metric capability breakdown of Jira forecasting tools.
* [`6-step-jira-execution.md`](6-step-jira-execution.md) — A copy-pasteable checklist for configuring the JQL, trial runs, and sample scoping for Jira dashboards.
* [`CHEATSHEET.md`](CHEATSHEET.md) — 1-page reference guide for explaining percentiles, the S-Curve, and Vacanti's four flow metrics to non-technical stakeholders.

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
Ayush Bisht is an AgileTools Specialist and Content Engineer dedicated to helping teams replace guesses with data. Read more agile workflows at [scrumdayindia.org](https://scrumdayindia.org/).
