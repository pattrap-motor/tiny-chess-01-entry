# Tiny chess engine (make.fun tiny-chess-01)

A compact Python chess program for the make.fun tiny-chess-01 gauntlet.
It is not a UCI engine: it plays games by talking HTTP to the competition
environment (POST /game, /move) as described by the competition rules.

Design: negamax alpha-beta search with iterative deepening under a fixed
node budget (fully deterministic — no wall-clock decisions), quiescence,
a transposition table, null-move pruning, late-move reductions and
killer/MVV-LVA ordering over a material + piece-square evaluation.
Repetition and the fifty-move rule are tracked from the game's move list.

`main.py` is the packed, self-contained entry point (standard library
only). Run it with the environment variables the harness provides:
MAKEFUN_ENV_URL, MAKEFUN_PROMPT_FILE, MAKEFUN_TRIAL_SEED.

MIT licensed — see LICENSE.
