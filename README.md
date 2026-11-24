# Tiny Chess Engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rayarvan77/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rayarvan77/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

## Overview

- Tiny UCI engine.
- For tiny-chess-01.
- Entry: Proper Sextant.
- Prize pool: $500.
- rayarvan77/tiny-chess-engine.
- Python 3.13.
- One move per pos.
- Eight house engines.

## Run

- Local env server first.
- Set MAKEFUN_ENV_URL.
- MAKEFUN_ENV_URL=http://127.0.0.1:8080
- python3 -P -s main.py
- Packed entry point.
- Packed: 4,036 bytes.
- Cap: 4,096 bytes.
- Payload: LZMA.
- Unpacked: 13,011 bytes.

## Board

- 0x88 board.
- 128 squares.
- Off-board test.
- Legal moves only.

## Search

- Alpha-beta search.
- Fixed node budget.
- Budget: 60,000 nodes.
- Deterministic.
- Iterative deepening.
- MVV-LVA ordering.
- Killer moves.
- History heuristic.
- Transposition table.
- Quiescence search.
- Futility pruning.
- Null-move pruning.
- Late move reductions.
- Mate-distance pruning.
- Ply-adjusted mates.

## Evaluation

- Piece-square tables.
- Tables are int lists.
- Pawn structure scored.
- Passed pawns via masks.
- Masks span files.
- Hash-keyed eval cache.
- Cache clears per move.
- Hit rate: 26-38%.
- Cache values identical.
- Non-pawn count.
- Guards null-move.

## Speed

- About 26,800 NPS.
- v1: about 16,570 NPS.
- Gain: about 1.6x.
- Mean: 1.9-2.5 s.
- Max: 7.2 s.
- Move limit: 10 s.
- v1: 8.5-13.1 s.
- v1 timed out each game.

## Trials

- Kit server trials.
- Trial 0: 3W, 3L.
- Trial 1: 3W, 3L.
- Elo: ~1,279.
- Elo floor: 1,154.
- Spare: 374/362.
- Beat depth-2.
- Beat depth-3.
- Beat nodes-100k.
- Beat nodes-250k.
- Lost depth-4 once.
- Lost nodes-100k once.
- Lost nodes-500k twice.
- Over 9 s: 0.
- Checked: 516 moves.
- v1 slow: 8/8.
- Wall: 502 s.
- Wall 2: 706 s.
- Limit: 1,800 s.

## Correctness

- Startpos d3: 8,902.
- Kiwipete d3: 97,862.
- Pos 3 d4: 43,238.
- Eval matches v1.
- Minified same.
- 3 positions checked.
- Same as source.

## v2 Changes

- Budget: 80k to 60k.
- Eval cache added.
- Pawn masks added.
- PSTs now int lists.
- Non-pawn counter.
- Mate-distance pruning.
- TT mates adjusted.
- PVS tried, dropped.
- PVS +15-26% nodes.
- Hit quiet spots.
- 1-letter names.
- LZMA1 packing.

## Leaderboard

- Top Elo: 2,110.
- Top record: 8-0.
- Top spare: 1,061.
- v2: no top-3 pick.
- Big step up.
- Up from round 2.
- Round 2 timed out.
- v2 stays in time.

## Files

- main.py: packed entry.
- README.md: this file.
- LICENSE: MIT license.

## License

- MIT license.
- See LICENSE for terms.
