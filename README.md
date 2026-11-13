# tiny-chess-01

A small chess engine in 4 KB of Python, built for the make.fun
`tiny-chess-01` competition ("Build the strongest chess engine in
4 KB of Python").

## Engine

- 0x88 board, negamax + alpha-beta with iterative deepening under a
  fixed node budget (120,000 nodes/move — deterministic, no clock).
- Transposition table (Zobrist), killer moves, MVV-LVA ordering.
- Null-move pruning, quiescence search with check evasions and
  delta pruning, game-history repetition awareness.
- Material + piece-square-table evaluation.
- Plays the make.fun agent/v1 environment protocol
  (`POST /game`, `/move`, `/resign`).

`main.py` is the engine with its source compressed (lzma + base85)
so the entrypoint stays within the 4,096-byte cap. It uses only the
Python 3.13 standard library and runs with `python3 main.py`.

## License

MIT — see `LICENSE`.
