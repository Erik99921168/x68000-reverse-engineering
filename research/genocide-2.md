# Genocide 2 — X68000 HP Research

Erik & Koyuki | 2026-09-27
Platform: RetroArch PX68K, V48 merged HDF

## Verified result

CPU address: $0553A2
Width: 16-bit
Continuous lock: FF01

V6 was tested in-game: the SHIELD bar remains full or refills after damage, and the effect persists across level transitions. The underlying game logic is not yet established.

## Experiment log

| Value | Observed result |
| --- | --- |
| 00C0 | Death on first hit |
| FFFF | Death on hit |
| FF00 | Empty SHIELD bar, survives repeated attacks and level transitions |
| FE00 | Empty SHIELD bar, survives; limited testing |
| FF01 | Full-bar survival and refill; works across levels |
| 0001 | Empty SHIELD bar, survives |

## Other experiments

- $05522E, 16-bit, 0004: movement caused a black screen.
- $0553A3, 8-bit, C0: death.
- $0553A3, 8-bit, 00: unexpected SHIELD-bar increase.

## Conclusion

Positive 0001 also produces survival, so negative signed values are not a sufficient explanation. The actual code mechanism remains unknown. Numeric-value testing is closed; FF01 is the preferred working cheat.

No game ROM, DIM, or HDF images are distributed.

Credits: Erik — testing and verification; Koyuki (ChatGPT) — analysis and documentation.
