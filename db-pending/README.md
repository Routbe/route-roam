# Held-back migrations

CONTRACT steps that remove legacy access. They stay out of `db/` (every file
there is replayed by the runners) until the deployed app uses the matching
EXPAND functions. Move a file into `db/` only when production runs that code
(the public health probe reports `schema` at or above the EXPAND number).


Applied and moved into `db/`: 0230, 0231, 0233, 0235, 0237 (production reported 0236).
- 0239 and 0241 applied (Nov 2026); no legacy rout_server access remains.
- 0262 applied on Neon (2026-11-13) and moved into `db/`.
- 0263 applied on Neon (2026-11-13); the app code using it is ready.
- 0264 waits for production to report schema >= 0263 (recovery requests through `rout_recovery_*`). On 2026-11-13 production still reported 0253.
