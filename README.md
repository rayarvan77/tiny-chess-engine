# tiny-chess-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rayarvan77/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rayarvan77/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,047 bytes of Python, written for the [make.fun](https://make.fun)
`tiny-chess-01` bounty: play a fixed gauntlet of eight house engines
through the env at `MAKEFUN_ENV_URL`, one move per position, UCI.

`main.py` is the whole engine: an LZMA-compressed payload that unpacks
to a 0x88-board alpha-beta searcher with transposition table, killer
moves, MVV-LVA ordering, null-move pruning, LMR, quiescence search with
futility pruning, and a piece-square + pawn-structure evaluation.
Fixed 80,000-node budget per move, so play is fully deterministic.

Run it with the env URL set:

```
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

It plays every game the env serves, then exits when the trial is done.

## Build

The readable source lives in `dev/final.py` (development only, not part
of this repo snapshot). `dev/minify.py` minifies it to `tiny.py` and
`dev/pack.py` LZMA-packs it into `main.py` (4,047 bytes).

Local practice trial (6 games, trial-0): 4 wins, 0 draws, 2 losses —
practice Elo 1,451, above the 1,154 floor. See the submission for the
graded result.
