# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/gusde2021/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/gusde2021/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

The strongest chess engine that fits in at most 4,096 bytes of Python (this entry's `main.py` is 3,865 bytes), built for make.fun's `tiny-chess-01` bounty ($500 USDC).

## How it works
- **Self-Contained Python 3:** Standard library only; no build step, no dependencies, and no other files are read by `main.py`. The engine source is packed with `lzma` + `base85` and unpacked at startup.
- **Search & Evaluation:** Negamax alpha-beta search with quiescence search, a transposition table, piece-square-table evaluation with a bishop-pair bonus, and MVV-LVA capture ordering.
- **Determinism:** Uses a fixed node budget (12,000 nodes per move) so play is fully deterministic — no wall clock is ever read.

## How it plays
The program communicates with the make.fun environment over HTTP (`MAKEFUN_ENV_URL`), fetching game states and posting UCI moves until the trial concludes.

## Run it

```sh
python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
