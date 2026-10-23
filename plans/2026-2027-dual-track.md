# 12-Month Dual-Track Plan | 2026-10-21 → 2027-10-21

**Status:** additive plan update, 2026-10-23. Do not restart or overwrite Day 1–30 progress.
**Allocation:** 50% AI Automation + Business · 30% Python / Software Engineering · 20% AI Trading Research.
**Guardrails:** no API top-ups for now; no real-money orders, leverage or exchange API execution. MuleRun Plus (three months via Rakyat Digital) is research/Agent experimentation; first BTC/ETH report completed, but its facts and predictions are unverified until independently checked.

| Month | Main focus | Specific deliverables | Acceptance / GitHub evidence |
|---|---|---|---|
| 1 | Python trading backtesting MVP alongside **existing Day 1–30 daily sprint** | Clean OHLCV dataset, baseline strategy, transaction cost + slippage, risk metrics, comparison with buy-and-hold/random, README; finish TuitionMate Day 5 tests | Reproducible `backtest.py`, config, CSV results, honest report; do not pretend prior poor backtests show edge |
| 2 | MuleRun + n8n and automation demo #1 | TuitionMate FAQ → human handoff workflow, 10-case QA, report of user needs | n8n export, FastAPI code, screenshots/tests |
| 3 | Automation demo #2 | Booking or lead intake with validation and safe fallback; MuleRun news report Agent evaluation | second working demo, model/report sources log |
| 4 | FastAPI fundamentals + API robustness | versioned endpoints, schemas, tests, rate limits, error paths | automated API test report |
| 5 | SQL + Docker | customer/lead schema using fictional test data, persistence, Docker Compose | migrations, Docker instructions, privacy checklist |
| 6 | Portfolio + initial customer discovery | 2 demonstrable projects, pricing draft, 3–5 conversations | case studies, demo videos, outreach record |
| 7 | Pilot project / service reliability | scope and contract templates, logs and handoff routing | supervised demo/pilot and incident checklist |
| 8 | Client acquisition + maintenance | onboarding checklist, manual backup, monitoring | operating procedures and client feedback |
| 9 | Paper trading (research only) | dry-run logs, exposure caps, kill switch, separate exchange sandbox if appropriate | audit logs and risk-review report; no real orders |
| 10 | Core portfolio work #1 | polished business automation project | tests, screenshots, README |
| 11 | Core portfolio work #2 and #3 | second automation + independently evaluated trading research project | 3 project demos and limitations |
| 12 | Career/business review | evidence-based income / portfolio / hiring-path assessment; future plan | annual retrospective and next-year choices |

## Day 1–30 continuity
1. Keep `plans/2026-10-sprint.md` unchanged and preserve closed Issues #1–#4.
2. Day 5 **Option B**: no OpenAI API充值; `ENABLE_CLOUD_AI=0`; run 10 predetermined FAQ tests, save CSV, then experiment with Ollama locally.
3. Continue Day 6–11 original service-demo and Freqtrade preparation while fitting Month 1 trading backtesting MVP into the 20% research allocation. Maintain earlier Python research.
4. Days 12–18: manually learn and test MuleRun Research Agent, verify sources, standardize report schema.
5. **Days 19–22**: only then attempt a read-only automated news report pipeline (export → validate → n8n → archive); functionality subject to MuleRun export/integration availability.
6. Days 23–30: stress test, backtest, document failure modes and review. Trading remains research-only.

## Format for each daily lesson
- **Learning goal:** 1–2 skills and project relevance
- **Coding tasks:** files, exact commands, expected outputs
- **Acceptance criteria:** reproducible checks before checking off
- **GitHub evidence:** code (without secrets), tests/CSV, README notes, issue checkbox after proof

## Trading MVP acceptance (Month 1)
- Data sorted, timestamped and checked for missing/duplicate candles and look-ahead
- Baseline backtest with explicit next-candle execution, fee/slippage assumptions, no leverage
- Return, drawdown, trade count, win rate, profit factor compared with buy-and-hold and random/baseline
- Reproduce with one command + pinned dependencies or documented versions
- Clearly state limitations and no verified profitability

## MuleRun Agent rules
- Source URL + article publication time + report generation timestamp in Malaysia time
- Separate facts / plausible interpretation / unsupported prediction
- Distinguish BTC and ETH data and original time windows
- Do not treat LLM report as signal, ground truth or automatic order authorization
- No wallet, exchange trading API keys, or personal data uploaded

## Day 5 task tracker
[Open Day 5 Issue](https://github.com/Stanford0903/ai-roadmap/issues/5). FAQ grounding is complete; 10-case log and secure demo code not yet verified. AI model integration moved to local offline evaluation while cloud credit balance is exhausted.
