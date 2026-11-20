[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![Rank](https://make.fun/badge/tiny-chess-01/cosmiklispos-design/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![Reward](https://make.fun/badge/tiny-chess-01/cosmiklispos-design/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01)

# tiny-chess

A chess engine in 4,096 bytes of Python, for make.fun `tiny-chess-01`.

`main.py` is the whole engine: an LZMA-compressed payload (standard library
only) that unpacks to a 0x88 negamax alpha-beta search with iterative
deepening, a transposition table, killer moves, quiescence search, null-move
pruning, check extensions, and a material + piece-square evaluation — under a
fixed 60,000-node budget per move, never a clock, so replays are deterministic.

It plays the house gauntlet through the env at `MAKEFUN_ENV_URL` (`/game`,
`/move`) until every game is over.

Build notes (dev sources, not part of the entry): the readable engine and the
minifier/packer live outside this repository; `main.py` here is the packed
artifact, 4,067 bytes.
