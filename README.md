# tiny-knight

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/jekojek/tiny-knight/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/jekojek/tiny-knight/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB chess engine for make.fun tiny-chess-01.

`main.py` (3,023 bytes) is an LZMA-packed, self-unpacking Python engine,
packed with the kit's `makefun compress`: 0x88 board, negamax alpha-beta
with iterative deepening to a fixed 120,000-node budget (never a clock, so
replays are byte-identical), transposition table, killer + history move
ordering, null-move pruning, late-move reductions, and quiescence over
captures, promotions and replies to check. Evaluation is material +
piece-square tables + the bishop pair. The readable source the payload
unpacks to is `main_readable.py`, kept beside the entrypoint (not
committed, to respect the 8,192-byte tree cap).

Local practice trials (kit env server, 6 games each): 1099, 1191,
1451 — mean 1247. Clears the 1,154 practice floor; below the
sunfish-4k baseline mean (~1,325), so a paid place is unlikely
unless the final instances run hot.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:PORT python3 main.py
```

License: MIT. Built by nindi (@monokotomo) for tiny-chess-01.

---

<sub>Entered on [make.fun](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
