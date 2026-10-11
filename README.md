<div align="center">

# Hi, I'm Manav

Building trading infrastructure where every statistic is honest by construction.

📫 [manavsingla1728@gmail.com](mailto:manavsingla1728@gmail.com)

</div>

---

### Flagship — [multi-asset-backtester](https://github.com/Manav0559/multi-asset-backtester)

**🔴 Live demo → [multi-asset-backtester.vercel.app](https://multi-asset-backtester.vercel.app)**
*(free-tier backend sleeps when idle — first load takes ~30–60s, then it's fast)*

Multi-asset backtesting + multiplayer paper trading, deployed end-to-end:

- **No-lookahead engine** — `position = signal.shift(1)` structurally, for user-submitted code too
- **Honest statistics** — Deflated Sharpe reported against the *actual* number of trials attempted, purged + embargoed walk-forward CV, triple-barrier meta-labeling, VaR/ES with Cornish-Fisher tails, factor attribution before anything is called alpha
- **Market frictions** — commission, spread, slippage, and square-root market impact in backtests; Reg-T-style short margin and 2× leverage on a row-locked, Decimal-exact shared ledger in paper trading
- **Bring-your-own-Python sandbox** — AST allowlist (no imports/dunders/exec) with line-numbered rejections at submission time
- FastAPI · PostgreSQL · Next.js · WebSockets · $0/month single-process deploy

[![CI](https://github.com/Manav0559/multi-asset-backtester/actions/workflows/ci.yml/badge.svg)](https://github.com/Manav0559/multi-asset-backtester/actions/workflows/ci.yml)

### Now building — [itch-lob-engine](https://github.com/Manav0559/itch-lob-engine)

NASDAQ TotalView-ITCH 5.0 order-book reconstruction in C++20: exchange binary
protocol parsing, order-id book, Catch2 tests, Linux + macOS CI.
**Project rule: no performance number ships unless a committed, reproducible
benchmark produced it.**
Dashboard: [manav0559.github.io/itch-lob-engine/dashboard/](https://manav0559.github.io/itch-lob-engine/dashboard/)

### Systems — [taskflow](https://github.com/Manav0559/taskflow)

Distributed job scheduler in Go: one-shot and cron jobs with DAG dependencies
behind a JWT-authenticated REST API, a leader-elected scheduler (Postgres
advisory lock), and workers that lease runs via `SELECT ... FOR UPDATE SKIP LOCKED`,
retry with exponential backoff and dead-letter permanent failures.
Prometheus + Grafana metrics; `docker compose up` brings up the whole stack.

### Networking — [xdp-gradient-aggregation](https://github.com/Manav0559/xdp-gradient-aggregation)

Reproduction of ATP (NSDI '21) in-network gradient aggregation on commodity
Linux with XDP/eBPF instead of a Tofino switch: Q16.16 fixed-point wire
protocol, user-space baselines, and an XDP aggregator that CI loads through the
real in-kernel verifier on a veth pair (generic/SKB mode) and drives with UDP
traffic, including malformed-packet cases.
Dashboard: [manav0559.github.io/xdp-gradient-aggregation/dashboard/](https://manav0559.github.io/xdp-gradient-aggregation/dashboard/)

---

### How I evaluate strategies

Purged walk-forward CV with embargo ≥ label horizon · Deflated Sharpe against
counted trials · transaction costs including square-root impact · factor
attribution to separate alpha from exposure · negative results reported, not
discarded.

### Stack

`Python` (FastAPI, pandas, scikit-learn, XGBoost, PyTorch) · `C++20` · `Go` · `C` · `eBPF/XDP` · `TypeScript` (Next.js) · `PostgreSQL` · `Docker` · `GitHub Actions`
