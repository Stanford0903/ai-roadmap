# AI Roadmap | 2026–2027

> Build useful AI products, develop reliable quantitative trading research, and document progress openly.

**Start:** 2026-10-21 · **12-month checkpoint:** 2027-10-21  
**Primary tracks (updated 2026-10-23):** AI Automation + Business (50%) · Python / Software Engineering (30%) · AI Trading Research (20%)

## Mission
1. Build and ship AI automation software that solves real business problems.
2. Learn software engineering through projects: Python, FastAPI, n8n, APIs, databases, Docker, testing, security, deployment.
3. Build a **research-only** crypto spot trading system using reproducible backtests and dry-run monitoring; **no live orders or leverage until independently evaluated**.
4. Demonstrate progress through completed projects, tests, GitHub commits, and customer feedback—not promises of profit.

## Updated 12-month roadmap
See [12-month dual-track learning plan](plans/2026-2027-dual-track.md). This is an additive refinement: all completed daily issues remain closed; the original October 21–31 sprint remains in place. The first month includes a Python trading backtesting MVP without disrupting TuitionMate Day 5. MuleRun Plus is used for research/agent experiments early and a *trial* of news report automation on Days 19–22; no real trading.

## Original 12-month milestone snapshot (historical)
| Period | AI Automation Business | AI Trading Research | Evidence |
|---|---|---|---|
| Oct–Dec 2026 | FAQ/booking assistant MVP, demo, initial customer interviews | Freqtrade setup, baseline backtests and risk rules | Demo + backtest report |
| Jan–Mar 2027 | Deliver a paid pilot if demand is confirmed | FreqAI and walk-forward research; compare costs and baselines | Client feedback + research report |
| Apr–Jun 2027 | Productize onboarding, support and monitoring | Dry-run only, alerts, kill switch and order audit | Stable dry-run logs |
| Jul–Oct 2027 | Portfolio of real case studies and customer acquisition process | Out-of-sample evaluation; continue research if no edge | Portfolio and annual review |

## October 2026 daily sprint
[**Open the October checklist**](plans/2026-10-sprint.md) and check off tasks in the corresponding **Issues**. Each issue has four specific checkboxes.

## How to track progress
- **Open issue** = day's work not finished.
- Tick `- [x]` in the issue body as individual tasks are verified.
- **Close issue** only after the day's deliverables are finished; link a commit, screenshot, short video or report.
- Blocked? Comment with error message and what was tried; do not pretend the task is complete.
- Write a short weekly reflection: learned, built, tested, questions, next focus.

## Active projects
- **AI Automation Business:** FAQ and appointment assistant prototype. Use fictional customer data until privacy and compliance are addressed.
- **AI Trading Research:** Keep earlier Python research intact. Transition engineering to Freqtrade; prioritize dry-run reliability, costs, leakage prevention and independent baseline comparisons.

### Historical research reminder
Previous exploratory BTC/USDT model with 24h cooldown: **-4.8967%**, while 1,000 matched-count random baselines averaged **-3.8631%** (training period only). **No established positive edge.** Do not use as a live-trading signal.

## Safety & scope
No credentials or API keys in commits; use `.env` ignored by Git. No real customer personal information in public repos. No real orders, leverage or exchange credentials for initial trading experiments. AI agents can assist research; an independent rule-based risk engine must control execution.

## Workload
Intensive October sprint: **4–5 hours/day** when available. Reduce to key tasks during university deadlines or other commitments. Protect sleep and rest.

**Next checkpoint:** 2026-10-31.
