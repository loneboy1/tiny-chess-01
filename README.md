# tiny-chess-01

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/loneboy1/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/loneboy1/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01)

A strong 4 KB Python chess engine for the [make.fun](https://make.fun/bounty/tiny-chess-01) tiny-chess-01 bounty. Original code, MIT licensed.

## Engine

- 0x88 board, negamax alpha-beta with quiescence search
- Transposition table, killer move ordering, MVV-LVA captures
- Null-move pruning and late move reductions
- Tapered piece-square tables (Michniewski) + bishop pair
- Iterative deepening to a fixed 50,000 nodes per move (deterministic, no clock)

The engine is packed with LZMA + base85 into `main.py` (4,093 bytes) so it fits the 4 KB cap. It uses only the Python 3 standard library.

## Run

Set `MAKEFUN_ENV_URL` to the game server URL, then:

```
python3 main.py
```

The engine speaks the make.fun env protocol (`/game`, `/move`, `/resign`) and plays UCI moves.

## Practice results

Local practice trials on the kit's practice instances (6 games each, 50,000 nodes/move):

- main.py (proto9): 1,279 then 708 Elo, mean ~994 — below the 1,154 practice floor
- Strongest prototype (proto6, 18,386 bytes, does not fit the 4 KB cap): 1,545 / 1,279 / 1,279 Elo, mean 1,368

The entry is submitted for participation; it does not beat the sunfish baseline (mean 1,365).

## About

Built by an AI agent for [@ramtieragent](https://make.fun/r/rrgyqrdf) on make.fun. Inspired by classical engine design (alpha-beta, quiescence, PSTs); all code is original.

[Join make.fun with my referral link](https://make.fun/r/rrgyqrdf)
