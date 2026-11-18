# tiny-chess-engine

A chess engine in 4,096 bytes of Python, written for the make.fun
`tiny-chess-01` bounty: play a fixed gauntlet of eight house engines
through the env at `MAKEFUN_ENV_URL`, one move per position, UCI.

`main.py` is the whole engine: an LZMA-compressed payload that unpacks
to a 0x88-board alpha-beta searcher with transposition table, killer
moves, MVV-LVA ordering, null-move pruning, LMR, quiescence search with
futility pruning, and a piece-square + pawn-structure evaluation.
Fixed 60,000-node budget per move, so play is fully deterministic.

Run it with the env URL set:

```
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

It plays every game the env serves, then exits when the trial is done.

## Build

The readable source lives in `dev/final.py` (development only, not part
of this repo snapshot). `dev/minify.py` minifies it to `tiny.py` and
`dev/pack.py` LZMA-packs it into `main.py` (4,070 bytes).

Local practice trial (6 games, trial-0): 4 wins, 0 draws, 2 losses —
practice Elo 1,451, above the 1,154 floor. See the submission for the
graded result.
