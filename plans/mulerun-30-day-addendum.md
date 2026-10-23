# MuleRun Addendum — 30-Day AI Trading System (2026-10-23)

> **Additive update only.** Preserve existing October AI Automation Business sprint, Days 1–4 accomplishments, Day 5 progress, and historical Python trading research. This document does not reset or replace the original roadmap.

## Overall allocation
- 60% AI Automation Business: TuitionMate FAQ/FastAPI/n8n MVP and client discovery.
- 30% AI Trading Research: preserve previous BTC/USDT Python work; backtest/Freqtrade research only.
- 10% review, documentation and verification.

## Status at adoption
- Day 1–4 learning issues completed; Day 5 ongoing.
- TuitionMate FAQ grounding and unknown-question handoff demonstrated. Cloud OpenAI API model call blocked by exhausted credits; proceed without充值 or cloud model calls.
- BTC/ETH MuleRun Market Research Report #1 generated as a one-time **research-only** test; do not count it as integration or proven trading signals.
- Existing BTC/USDT backtest outcomes remain negative / inconclusive; no demonstrated tradable edge.

## MuleRun staged integration
| Day | MuleRun add-on only | Main track preserved | Completion evidence |
|---|---|---|---|
| 1–4 | No retroactive change | Completed n8n/FastAPI/product work | Closed issues |
| 5–7 | Read first BTC/ETH report; tag facts vs inferences vs forecasts; verify links and timestamps | Finish FAQ 10-case test, explore offline/local LLM | Annotated report + CSV |
| 8–14 | Manual research-agent prompts; check BTC/ETH news, macro catalysts, source dates and contradictory articles; compare to primary data | Continue existing Python trading research, Docker/Freqtrade setup and backtests | Source-verification log |
| 15–18 | Define research report schema (date/timezone, snapshot, BTC/ETH price, 24h change, news with URL+publication time, confidence/unknowns, risk events) | Preserve ML validation, walk-forward and risk work | Report schema + quality checklist |
| **19** | Pilot one read-only MuleRun report export (manual download or official export if available) | No broker connections | Saved report |
| **20** | Parse report into JSON/Markdown; mark unverifiable fields as missing rather than inventing them | Data-validation code | Validator output |
| **21** | n8n workflow to ingest local/report file and save archive; notification optional | No trades | Successful local run |
| **22** | Test automation end-to-end, missing sources, stale data, duplicate reports and failures | Human approval before sharing report | Test log |
| 23–28 | Evaluate repeatability and quality; optionally dry-run research alerts, never orders | Freqtrade historical backtest or dry run, risk rules intact | QA + backtest notes |
| 29–30 | Compare outcomes, time spent, plan for next month | Original 30-day review | Monthly report |

## Research Agent boundaries
- Read-only public market data and news, no exchange login/wallet/API credentials/order access.
- Facts require source link, timestamp, unit and timezone; label unverified numbers.
- AI interpretations separated from source facts; no certainty language or trading guarantees.
- Automated output needs deduplication and human review; any trading model is evaluated separately.
- MuleRun Plus credit/subscription details can change; confirm in-product before scheduled research jobs.
- No live orders, no leverage, no real-money trading.

## Tracking
- GitHub Day 5 issue remains open until 10 scenarios and demo evidence are verified.
- Keep MuleRun add-on separate from already completed tasks; no retroactive checkbox changes.
