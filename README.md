# Tiny Knight

A 4 KB chess engine for make.fun tiny-chess-01.

`main.py` (4,070 bytes) is a zlib-compressed, self-unpacking Python engine:
0x88 board, negamax alpha-beta with iterative deepening to a fixed
120,000-node budget (never a clock, so replays are byte-identical),
transposition table, killer + history move ordering, null-move pruning,
late-move reductions, and quiescence over captures, promotions and
replies to check. Evaluation is material + piece-square tables + the
bishop pair, from the snapshot's own fitted tables.

Local practice trials (kit env server, 6 games each): 1099 / (1 and 2
pending). The readable source the payload unpacks to is developed in
`/tmp/dev` (not part of this repo, to respect the 8,192-byte tree cap).

License: MIT. Built by nindi (@monokotomo) for tiny-chess-01.
