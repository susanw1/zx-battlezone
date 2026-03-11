# Battlezone Symbol Glossary

Status: seed version

Purpose: cross-reference notebook symbols, likely meanings, and future disassembly mappings for Quicksilva `Battlezone`.

Conventions:

- `Kind` distinguishes code entry points from data/state symbols.
- `Meaning` is a best current reading, not always code-confirmed.
- `Evidence` names the current source for the interpretation.
- `Address` is left blank until mapped into the disassembly.

| Symbol | Kind | Meaning | Evidence | Address | Notes |
| --- | --- | --- | --- | --- | --- |
| `EXST1` | Data | Entity existence bitfield | `Red-book-scan1` page 4 |  | Page 4 lists bits for old tank, super tank, saucer, missile, my bullet, his bullet. |
| `EXST2` | Data | Explosion existence bitfield mirroring `EXST1` categories | `Red-book-scan1` page 4 |  | Page 4 says "as above but explosions". |
| `PRSTA` | Data | Priority/state field controlling active subsystems or render/update order | `Red-book-scan1` pages 7, 10, 11; `zx-battlezone/README.md` |  | Needs confirmation from code. Page 10 lists entity/state values against it. |
| `TKSTR` | Data | Tank strategy/state byte | `Red-book-scan1` pages 10, 13; Susan recollection |  | Tracks modes such as trundling, stopping, and attacking. |
| `TKMCT` | Data | Tank manoeuvre/frame counter | `Red-book-scan1` pages 7, 13; Susan recollection |  | Attack transition delay likely depends on score. |
| `TKDIR` | Data | Tank direction | `Red-book-scan1` pages 5, 9, 11, 13 |  | Often stored alongside `TKOR`. |
| `TKOR` | Data | Tank orientation | `Red-book-scan1` pages 5, 13, 15, 16 |  | Likely heading/orientation angle or vector index. |
| `TKX` | Data | Tank X coordinate | `Red-book-scan1` pages 9, 11, 13 |  | World-space, player-relative in current recollection. |
| `TKZ` | Data | Tank Z coordinate | `Red-book-scan1` pages 9, 11, 13 |  | World-space, player-relative in current recollection. |
| `TEXST` | Code | Tank existence / tank spawn routine | `Red-book-scan1` pages 11-12 |  | Strong routine heading evidence. |
| `TKSTRAT` | Code | Tank strategy routine | `Red-book-scan1` pages 13-16; Susan recollection |  | Shared tank/supertank logic with a few conditionals. |
| `SAUC` | Code | Saucer existence/render routine | `Red-book-scan1` page 17 |  | Ends by jumping to bullet handling. |
| `SAUSTRAT` | Code | Saucer movement strategy routine | `Red-book-scan1` page 18 |  | Uses `SAMCT`, `SAUX`, `SAUZ`. |
| `SAMCT` | Data | Saucer manoeuvre/frame counter | `Red-book-scan1` page 18 |  | Parallel to `TKMCT` / `MSMCT`. |
| `SAUX` | Data | Saucer X coordinate | `Red-book-scan1` pages 17-18 |  |  |
| `SAUZ` | Data | Saucer Z coordinate | `Red-book-scan1` pages 17-18 |  |  |
| `SAUOR` | Data | Saucer orientation | `Red-book-scan1` page 17 |  | Likely render or movement heading. |
| `MISSILES` | Code | Missile existence/render routine | `Red-book-scan1` pages 19-20 |  | Calls `MISSTRAT` and perspective/radar code. |
| `MISSTRAT` | Code | Missile strategy state machine | `Red-book-scan1` page 21; Susan recollection |  | Missiles zig-zag left/right, return to original path, and hop over obstacles. |
| `MSTRJ` | Data | Missile strategy/action bitfield | `Red-book-scan1` page 6; Susan recollection |  | Encodes current missile action, including zig-zag and up/down obstacle-hop flags. |
| `MSTRT` | Data | Unknown missile-related symbol | `Red-book-scan1` pages 20-21; Susan recollection |  | Not yet identified. Susan is confident `MSTRJ` is the missile action bitfield, so `MSTRT` should be treated as unresolved rather than assumed equivalent. |
| `MSMCT` | Data | Missile manoeuvre counter | `Red-book-scan1` pages 6-7 |  | Page 6 gloss: "No. frame since manoeuvre". |
| `MISCT` | Data | Missile count so far | `Red-book-scan1` page 6; Susan recollection |  | Difficulty increases by allowing one more zig per missile as the game progresses. |
| `ZIG` | Data | Number of zigzags available | `Red-book-scan1` page 6; Susan recollection |  | Increases with missile number/difficulty. |
| `MISX` | Data | Missile X coordinate | `Red-book-scan1` pages 6, 19, 21 |  |  |
| `MISY` | Data | Missile Y coordinate | `Red-book-scan1` pages 6, 21 |  | Used for missile hop-over motion. |
| `MISZ` | Data | Missile Z coordinate | `Red-book-scan1` pages 6, 19, 21 |  |  |
| `MSOR` | Data | Missile orientation or movement offset register | `Red-book-scan1` pages 19-21 |  | Adjusted repeatedly in `MISSTRAT`. |
| `HBLCT` | Data | Hostile bullet count or timer | `Red-book-scan1` page 11 |  | Part of hostile bullet initialization block. |
| `HBLOR` | Data | Hostile bullet orientation | `Red-book-scan1` page 11 |  | Likely heading/orientation for enemy shell. |
| `HBLX` | Data | Hostile bullet X coordinate | `Red-book-scan1` page 11 |  |  |
| `HBLZ` | Data | Hostile bullet Z coordinate | `Red-book-scan1` page 11 |  |  |
| `HBULZ` | Data | Hostile bullet Z coordinate or derived Z slot | `Red-book-scan1` page 11 |  | Needs reconciliation with `HBLZ`. |
| `OB1` | Data | Obstacle 1, cube | `Red-book-scan1` page 10 |  | Sketch confirms cube-like object. |
| `OB2` | Data | Obstacle 2, cube | `Red-book-scan1` page 10 |  | Sketch confirms cube-like object. |
| `OB3` | Data | Obstacle 3, pyramid | `Red-book-scan1` page 10 |  | Sketch confirms pyramid-like object. |
| `OB4` | Data | Obstacle 4, low block | `Red-book-scan1` page 10 |  | Sketch confirms low rectangular block. |
| `XLOC` | Data | X-local or transformed X coordinate slot | `Red-book-scan1` pages 1-3 |  | Early transform notes. |
| `ZLOC` | Data | Z-local or transformed Z coordinate slot | `Red-book-scan1` pages 1-3 |  | Early transform notes. |
| `SP1` | Data | Temporary storage for stack pointer | `Mem-locations.pdf`; Susan recollection |  | Used when `SP` is repurposed as a general address register inside a routine and must be restored before `CALL`/`RET`. |
| `SP2` | Data | Secondary temporary storage for stack pointer | `Mem-locations.pdf`; Susan recollection |  | Likely used when `SP1` is already in use in a caller. |
| `XPERS` | Data | X perspective value or pointer | `Red-book-scan1` pages 1, 15, 16, 17 |  | Mentioned in perspective-related pages. |
| `YPERS` | Data | Y perspective value or pointer | `Red-book-scan1` pages 17, 19 |  |  |
| `PERSP` | Code | Perspective routine | `Red-book-scan1` pages 15-17, 19 |  | Strong call-site evidence. |
| `LINCD` | Code | Line-code / line-definition selector | `Red-book-scan1` pages 15, 17, 20 |  | Likely chooses visible line sets by view. |
| `LNLPT` | Code | Line plotting routine | `Red-book-scan1` pages 15-17, 20 |  | Strong call-site evidence. |
| `RADAR` | Code | Radar update routine | `Red-book-scan1` pages 9, 19 |  |  |
| `KEMPST` | Code | Kempston joystick decode routine | `Red-book-scan2` pages 9-10; `battlezone.skool` | `0xAD3E` | Reads port `0x1F` and converts Kempston directions/fire into the movement bitfield consumed by the input interpreter. |
| `KEYIN` | Code | Keyboard/input interpretation block | `Red-book-scan2` pages 9-10; `battlezone.skool` | `0xA685` `[entry within larger routine]` | Merges Kempston and keyboard input, masks invalid movement bits near obstacles, and prepares movement/turn handling. |
| `MESPR` | Code | Message/rectangle print routine | `Red-book-scan1` pages 7, 9, 19; `battlezone.skool` | `0x9452` | Copies a rectangular block described as destination, height, width, then data. Used for messages and other small UI blocks. |
| `MESER` | Code | Message/rectangle erase routine | `zx-battlezone/docs/index.md`, `Red-book-scan2` index notes; `battlezone.skool` | `0x9476` | Erases a rectangle using the same descriptor format as `MESPR`. |
| `SCOPR` | Code | Score-update routine | `Red-book-scan2` page 17; `battlezone.skool` | `0x94AC` | Adds a packed-BCD increment, checks the extra-life threshold, and falls through into `NUMBA`. |
| `NUMBA` | Code | Number/score display routine | `Red-book-scan2` page 19; `battlezone.skool` | `0x94EC` | Renders the current packed-BCD value using the digit glyph table at `0xCD80`. |
| `POLCO` | Code | Polar-coordinate helper or position/orientation calculator | `Red-book-scan1` pages 5, 19 |  | Name suggests polar conversion; needs code confirmation. |
| `MATOLT` | Code | Maths/helper routine, exact expansion unclear | `Red-book-scan1` page 15 |  | Needs code confirmation. |
| `MATRT1` | Code | Maths/helper routine, exact expansion unclear | `Red-book-scan1` page 15 |  | Needs code confirmation. |
| `DLAY1` | Code | Delay or timing helper | `Red-book-scan1` pages 15-17, 19 |  | Likely frame pacing / timed visual delay. |
| `FRAME` | Data | Frame counter | `Red-book-scan1` pages 7, 11, 13 |  | Strong evidence from name and usage. |
| `PHASE` | Data | Phase/state byte | `Red-book-scan1` pages 7, 13 |  | Likely attract/demo or movement-related substate. |
| `SCORE` | Data | Score | `Red-book-scan1` pages 5, 7 |  |  |
| `SHIP` | Data | Lives/ships count | `Red-book-scan1` page 7 |  | Likely matches `Lives` variable in current disassembly. |
| `TRIGA` | Data | Trig angle or trig-table selector | `Red-book-scan1` pages 7, 11 |  | Needs code confirmation. |
| `XTAB` | Data | X-coordinate table | `Red-book-scan1` page 9; `docs/index.md` |  | Likely entity vertex or object position table. |
| `ZTAB` | Data | Z-coordinate table | `Red-book-scan1` page 9; `docs/index.md` |  | Likely entity vertex or object position table. |
| `VU-A` | Data | View bucket A | `Red-book-scan1` pages 15-16, 20 |  | One of several view-dependent line sets. |
| `VU-B` | Data | View bucket B | `Red-book-scan1` pages 15-16, 20 |  |  |
| `VU-C` | Data | View bucket C | `Red-book-scan1` pages 15-16, 20 |  |  |
| `VU-D` | Data | View bucket D | `Red-book-scan1` pages 15-16 |  |  |
| `VU-E` | Data | View bucket E | `Red-book-scan1` pages 15-16 |  |  |

## Immediate next mappings

- Identify `MSTRT`.
- Map `PRSTA` and `EXST1`/`EXST2` into concrete disassembly variables.
- Locate `PERSP`, `LINCD`, `LNLPT`, `RADAR`, and `POLCO` in `battlezone-skoolkit/sources/battlezone.skool`.
- Map `SCREEN`, `KBORD INTERPRETATION`, `TABS`, and `LINCDS`.
