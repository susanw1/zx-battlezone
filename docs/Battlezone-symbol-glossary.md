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
| `EXST1` | Data | Active-entity existence/state byte | `Red-book-scan1` page 4; `battlezone.skool` | `0xFE6A` `[probable]` | Current best read: tank/supertank, saucer, missile, my bullet, and his bullet occupy the upper bits; the low bits are reused for obstacle/object family state (`0` none, `1` low block, `2` cube family, `3` pyramid). |
| `EXST2` | Data | Deferred explosion / respawn state byte mirroring `EXST1` categories | `Red-book-scan1` page 4; `battlezone.skool` | `0xFE6C` `[probable]` | Set when entities transition into explosion/effect paths; high bits are later ORed back into `0xFE6A` before reinitialisation at `0x9644`. |
| `PRSTA` | Data | Current render/visibility state byte | `Red-book-scan1` pages 7, 10, 11; `battlezone.skool` | `0xFE6E` `[probable]` | Best current match for the notebook's state layout: visibility-tested/render-active counterpart to `EXST1`, including obstacle/object low-bit state. Current best refinement: the high nibble mirrors the visible/drawable subset of `EXST1`. |
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
| `XPERS` | Data | X perspective output buffer / workspace pointer target | `Red-book-scan1` pages 1, 15, 16, 17; `Red-book-scan2` page 25; `battlezone.skool`; Susan follow-up | `0xDE90` `[buffer base]`; `FE38` `[workspace end-pointer]` | The notebook's `56976` reading is consistent with the code using `SP` as a descending write pointer into the buffer. Current code often samples interior words such as `0xDE92`, `0xDE98`, and `0xDE9E`. |
| `YPERS` | Data | Y perspective output buffer / workspace pointer target | `Red-book-scan1` pages 17, 19; `Red-book-scan2` page 25; `battlezone.skool` | `0xDEC8` `[buffer base]`; `FE3A` `[workspace end-pointer]` | Used in the same descending-`SP` style as `XPERS`; current code often samples interior words such as `0xDED0` and `0xDED6`. |
| `PERSP` | Code | Perspective routine | `Red-book-scan1` pages 15-17, 19 |  | Strong call-site evidence. |
| `LINCD` | Code | Line-code / line-definition selector | `Red-book-scan1` pages 15, 17, 20 |  | Likely chooses visible line sets by view. |
| `LNLPT` | Code | Line plotting routine | `Red-book-scan1` pages 15-17, 20; `battlezone.skool` | `0x805C` `[probable]` | Strong current-best match: consumes `LINCDS` blocks as a 1-byte line count followed by one four-pointer record per line. |
| `RADAR` | Code | Radar update routine | `Red-book-scan1` pages 9, 19 |  |  |
| `SCREEN` | Code | Late-frame screen/hill/status pipeline | `Red-book-scan2` page 7; `battlezone.skool`; Susan recollection | `0xA5AE` `[phase within MainGameLoop]` | Current best match is the phase that calls `MHLC`, `SHLC`, two unresolved hill plot helpers, then `SDRAW`. |
| `SDRAW` | Code | Present-and-clear screen draw routine | `Red-book-scan2` page 7; `battlezone.skool` | `0x8C3C` | Copies the off-screen buffers to the visible Spectrum screen and clears the working buffers afterwards. |
| `MHLC` | Code | Probable main-hill limit calculation | `Red-book-scan2` page 7; `battlezone.skool` | `0x8D68` | Derives a clipped hill-bound pair in `FE24/FE26`. |
| `SHLC` | Code | Probable secondary-hill limit calculation | `Red-book-scan2` page 7; `battlezone.skool` | `0x8E08` | Consumes `FE24/FE26` and derives `FE28/FE2A`. |
| `MHLPT` | Code | Probable main-hill plotting routine | `Red-book-scan2` page 7; `battlezone.skool` | `0x8E38` | Uses the hill pointer at `FE2C` together with the main-hill limits from `MHLC`. |
| `SHLPT` | Code | Probable secondary-hill plotting routine | `Red-book-scan2` page 7; `battlezone.skool` | `0x8F53` | Reuses the hill plot core with the secondary limits from `SHLC`. |
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
| `YLOC` | Data | Y-location / Y-coordinate table family | `Red-book-scan2` pages 23-25; `battlezone.skool` | `0xDBB8` `[table start]`; `FE34` `[workspace pointer]` | Current code often uses interior offsets such as `0xDBC0`. |
| `XTAB` | Data | X-coordinate table | `Red-book-scan1` page 9; `Red-book-scan2` pages 23-25; `battlezone.skool` | `0xD9D0` `[table start]`; `FE32`/`FE42` `[workspace pointers]` | Current code also uses interior offsets such as `0xD9D8`. |
| `ZTAB` | Data | Z-coordinate table | `Red-book-scan1` page 9; `Red-book-scan2` pages 23-25; `battlezone.skool` | `0xDAC4` `[table start]`; `FE36`/`FE46` `[workspace pointers]` | Current code also uses interior offsets such as `0xDACC`. |
| `HBLXLC` | Data | Hostile-bullet X-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDD20` | Loaded into the `FE32` table pointer for hostile bullet drawing. |
| `HBLZLC` | Data | Hostile-bullet Z-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDDD0` | Loaded into the `FE36` table pointer for hostile bullet drawing. |
| `OBXLC` | Data | Obstacle X-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDD28` | Loaded into the `FE32` table pointer for obstacle drawing. |
| `OBZLC` | Data | Obstacle Z-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDDD8` | Loaded into the `FE36` table pointer for obstacle drawing. |
| `EXXLC` | Data | Explosion X-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDD36` | Loaded into the `FE32` table pointer for explosion-related drawing. |
| `EXZLC` | Data | Explosion Z-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDDE6` | Loaded into the `FE36` table pointer for explosion-related drawing. |
| `EXBXL` | Data | Explosion auxiliary X-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDD6E` | Used by the later explosion/secondary-effect path starting at `0xAAAF`. |
| `EXBZL` | Data | Explosion auxiliary Z-location table | `Red-book-scan2` pages 24-25; `battlezone.skool` | `0xDE1E` | Used by the later explosion/secondary-effect path starting at `0xAAAF`. |
| `MISS` | Data | Missile visible-line family with three ordered view slots | `Red-book-scan2` page 21; `battlezone.skool` | `0xD392`, `0xD3DC`, `0xD43E` `[probable]` | Current best read: selected at `0xA080` in the missile render path by comparing projected X values at `0xDE98/0xDE9A/0xDE9C`. `0xD3DC` is the larger middle family; `0xD392` and `0xD43E` look like mirrored side-view counterparts. |
| `MBLVU` | Data | My-bullet visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD488` `[probable shared family]` | Current best read is that the same line-data family is reused for both my bullet and hostile bullet. |
| `HBLVU` | Data | Hostile-bullet visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD488` `[probable shared family]` | Current best read is that the same line-data family is reused for both my bullet and hostile bullet. |
| `OB1VU` | Data | Obstacle 1 visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD4A2` `[probable shared cube-family base]` | Current best read: shared with `OB2VU`; three current-best view slots at `0xD4A2`, `0xD4DE`, `0xD51A`. |
| `OB2VU` | Data | Obstacle 2 visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD4A2` `[probable shared cube-family base]` | Current best read: shared with `OB1VU`; three current-best view slots at `0xD4A2`, `0xD4DE`, `0xD51A`. |
| `OB3VU` | Data | Obstacle 3 visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD554` `[probable family base]` | Current best read: three current-best view slots at `0xD554`, `0xD590`, `0xD5CC`. |
| `OB4VU` | Data | Obstacle 4 visible-line family | `Red-book-scan2` page 21; `battlezone.skool` | `0xD5F6` `[probable family base]` | Current best read: three current-best view slots at `0xD5F6`, `0xD632`, `0xD66E`. |
| `CRAVU` | Data | Crash-view visible-line family | `Red-book-scan2` page 17 |  | Currently unresolved again. Earlier mapping to `0xD392/0xD3DC/0xD43E` was wrong; those addresses are a better match for page-21 `MISS`. |
| `VU-A` | Data | View bucket A | `Red-book-scan1` pages 15-16, 20 |  | One of several view-dependent line sets. |
| `VU-B` | Data | View bucket B | `Red-book-scan1` pages 15-16, 20 |  |  |
| `VU-C` | Data | View bucket C | `Red-book-scan1` pages 15-16, 20 |  |  |
| `VU-D` | Data | View bucket D | `Red-book-scan1` pages 15-16 |  |  |
| `VU-E` | Data | View bucket E | `Red-book-scan1` pages 15-16 |  |  |

## Current `LINCDS` notes

- The `0xA37B` selector in `battlezone.skool` is now treated as a probable obstacle-view `LINCDS` chooser.
- Current best read:
  - `0xD488` = probable shared bullet visible-line family (`MBLVU` / `HBLVU`)
  - `0xD4A2` = probable shared cube-family line-data base for `OB1VU` / `OB2VU`
    - current best view slots: `0xD4A2`, `0xD4DE`, `0xD51A`
  - `0xD554` = probable pyramid-family line-data base for `OB3VU`
    - current best view slots: `0xD554`, `0xD590`, `0xD5CC`
  - `0xD5F6` = probable low-block-family line-data base for `OB4VU`
    - current best view slots: `0xD5F6`, `0xD632`, `0xD66E`
  - current best interpretation of the selector at `0xA576`: it adds `0x00`, `0x3C`, or `0x78` to the family base to pick one of three precomputed obstacle-view slots
- The explosion / crash side now has a cautious first-pass mapping:
  - `0xD6B8` = probable `TKEXV` family, used by the tank / supertank explosion path
  - `0xD7CC` = probable `SAEXV` family, used by the saucer explosion path
  - `0xD8B0` = probable `MSEXV` family, used by the missile explosion path
  - `0xD95C` = probable `EXBLT` family, used by the later bullet-impact / bullet-explosion path
  - `0xD392`, `0xD3DC`, `0xD43E` are now better understood as ordered missile-view families from page-21 `MISS`
  - `CRAVU` remains unresolved

## Immediate next mappings

- Identify `MSTRT`.
- Map `PRSTA` and `EXST1`/`EXST2` into concrete disassembly variables.
- Locate `PERSP`, `LINCD`, `LNLPT`, `RADAR`, and `POLCO` in `battlezone-skoolkit/sources/battlezone.skool`.
- Tighten the remaining `LINCDS` / view-line-family mappings, especially the exact crash-view mapping for notebook `CRAVU` and the remaining non-obstacle families around `D95C`.
