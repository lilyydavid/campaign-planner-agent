
# Agentic Engine for Campaign Planning & RGM

A multi-agent system that plans, stress-tests, and recalibrates promotional campaigns in real time.

## Demo

https://github.com/user-attachments/assets/cf56c393-cd22-4b9b-975e-8ff2d24f905b

## What it does

Given a sales target, mechanic, and campaign window, the engine:

1. **Plans** — evaluates the full offer taxonomy (GWP, flat-discount, bundle, tiered-spend, power-hour) against historical campaign comps and recommends the strongest mechanic with a ranked set of alternatives
2. **Stress-tests** — runs downside scenarios (traffic shock, ABV compression, discount stack breach, tier mix drift) and flags which risks are controllable vs macro
3. **Recalibrates** — monitors live sales against power-hour-weighted landing targets and surfaces recovery levers when actuals diverge

## Architecture

- **Planner agent** — mechanic selection, tier-level revenue forecasting, confidence scoring
- **Sentinel agent** — live recalibration against intraday power-hour curves
- **Stress tester agent** — scenario simulation across 6 downside cases per candidate
- **Pipeline** — orchestrates agent calls, manages state, routes demo vs live mode