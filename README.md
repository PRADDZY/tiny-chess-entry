# Tiny Chess Search

A deterministic chess engine for [make.fun tiny-chess-01](https://make.fun/bounty/tiny-chess-01), packed as a Python entrypoint under the 4 KB limit.

The engine uses a 0x88 board, tapered PeSTO evaluation, iterative-deepening PVS, a transposition table, and capture/check quiescence. A per-scenario profile selects the search budget and move-ordering salt by opponent and colour; a scenario-keyed opening book supplies early moves before search takes over.

The game protocol and original copyright notice come from make.fun's MIT-licensed starter; see `LICENSE`.

Run with Python 3.13 in the competition environment, which supplies `MAKEFUN_ENV_URL`.

## Measured results

The kit's local `practice/trial-0` scorer records 2,112 Elo, six wins, no draws or losses, and 923 spare plies. Separate local checks against `nodes-1M` on King's Indian Attack and `nodes-2M` on Bird's Opening ended in mate after 79 and 96 plies. Together these eight cases total 1,148 spare plies; that is local evidence, not a published leaderboard score.
