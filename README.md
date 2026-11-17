# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/farah2222/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/farah2222/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An entry in the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01): a compact chess engine in one Python file.

## The engine

`main.py` (3,298 bytes) is an LZMA-compressed payload that unpacks and
execs the engine. It is a 0x88-board alpha-beta searcher: negamax with
quiescence (captures, promotions, replies to checks), a transposition
table with ply-adjusted mate scores, MVV-LVA capture ordering, killer
moves, null-move pruning, and check extensions, under a fixed
150,000-node budget per move (deterministic — no clock, no randomness).
Evaluation is material plus procedural piece-square terms, a bishop-pair
bonus, passed-pawn bonuses, and a king pawn-shield term.

## Strength

Practice Elo (6-game trials, house gauntlet): trial 0 = 1,451,
trial 1 = 1,279, trial 2 = 1,451; mean ≈ 1,394 — above the house
baseline (~1,365) and the 1,154 final floor.

## Files

- `main.py` — the whole engine (compressed, ≤ 4,096 bytes).
- `LICENSE` — MIT.
