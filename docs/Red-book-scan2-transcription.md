# Red Book Scan 2 Transcription

Source PDF: [Red-book-scan2.pdf](Red-book-scan2.pdf)

Extracted page images:

- [page-01.png](extracted/red-book-scan2/page-01.png)
- [page-02.png](extracted/red-book-scan2/page-02.png)
- [page-03.png](extracted/red-book-scan2/page-03.png)
- [page-04.png](extracted/red-book-scan2/page-04.png)
- [page-05.png](extracted/red-book-scan2/page-05.png)
- [page-06.png](extracted/red-book-scan2/page-06.png)
- [page-07.png](extracted/red-book-scan2/page-07.png)
- [page-08.png](extracted/red-book-scan2/page-08.png)
- [page-09.png](extracted/red-book-scan2/page-09.png)
- [page-10.png](extracted/red-book-scan2/page-10.png)
- [page-11.png](extracted/red-book-scan2/page-11.png)
- [page-12.png](extracted/red-book-scan2/page-12.png)
- [page-13.png](extracted/red-book-scan2/page-13.png)
- [page-14.png](extracted/red-book-scan2/page-14.png)
- [page-15.png](extracted/red-book-scan2/page-15.png)
- [page-16.png](extracted/red-book-scan2/page-16.png)
- [page-17.png](extracted/red-book-scan2/page-17.png)
- [page-18.png](extracted/red-book-scan2/page-18.png)
- [page-19.png](extracted/red-book-scan2/page-19.png)
- [page-20.png](extracted/red-book-scan2/page-20.png)
- [page-21.png](extracted/red-book-scan2/page-21.png)
- [page-22.png](extracted/red-book-scan2/page-22.png)
- [page-23.png](extracted/red-book-scan2/page-23.png)
- [page-24.png](extracted/red-book-scan2/page-24.png)
- [page-25.png](extracted/red-book-scan2/page-25.png)
- [page-26.png](extracted/red-book-scan2/page-26.png)
- [page-27.png](extracted/red-book-scan2/page-27.png)
- [page-28.png](extracted/red-book-scan2/page-28.png)

Status: first pass

## Overview

This notebook continues the code-level design notes from `Red-book-scan1`. The current pass is a structured page map with exact readings where sampled, and topic-level notes elsewhere based on both page inspection and the existing [index.md](index.md).

## Page 1

Image: [page-01.png](extracted/red-book-scan2/page-01.png)

Heading:

- `BULLT`

Visible variables and calls include:

- `(EXST1)`
- `OBT`
- `HBLT`
- `(MBBCT)` `[unclear]`
- `(MBXLC+2)`
- `(MBZLC+2)`
- `(XDIS)`
- `(ZDIS)`
- `(XTAB)`
- `(ZTAB)`
- `CALL MATMLT`
- `(XPERS)`
- `(YPERS)`
- `CALL PERSP`
- `(PRSTA)`
- `CALL DLAY1`
- `(SPPL)`
- `(XMAX)`
- `(XMIN)`

Notes:

- This is player bullet handling and rendering.

## Page 2

Image: [page-02.png](extracted/red-book-scan2/page-02.png)

- Not yet closely reviewed.
- Likely continuation of `BULLT`.

## Pages 3-4

Images:

- [page-03.png](extracted/red-book-scan2/page-03.png)
- [page-04.png](extracted/red-book-scan2/page-04.png)

Heading on page 3:

- `HBULLT`

Visible content from sampled page 3:

- Hostile bullet update/render logic.
- Uses:
  - `(HBLCT)`
  - `(HBLOR)`
  - `(HBULX)`
  - `(HBULZ)`
  - `(XDIS)`
  - `(ZDIS)`
  - `(XTAB)`
  - `(ZTAB)`
  - `CALL MATMLT`
  - `CALL PERSP`
  - `(PRSTA)`
  - `CALL DLAY`
  - `(MAX2)`
  - `(MIN2)`
  - `CALL HBEXP`

## Pages 5-6

Images:

- [page-05.png](extracted/red-book-scan2/page-05.png)
- [page-06.png](extracted/red-book-scan2/page-06.png)

Heading on page 5:

- `OBJECTS`

Visible content from sampled page 5:

- Obstacle handling using:
  - `(OB1Z)`
  - `(OB1X)`
  - `(OB2Z)`
  - `(OB3X)`
  - `(OB4X)`
  - `(XDIS)`
  - `(ZDIS)`
  - `(OBOR)`
  - `CALL MATMLT`
  - `CALL PERSP`
  - `CALL SCREEN`
  - `CALL LNLPT`

## Page 7

Image: [page-07.png](extracted/red-book-scan2/page-07.png)

Heading:

- `SCREEN`

Visible calls include:

- `CALL MHLC`
- `CALL SHLC`
- `CALL EBASE`
- `CALL SDRAW`
- `CALL MHLPT`
- `CALL SHLPT`

Notes:

- This looks like sights/hills/screen-overlay work, matching the guess in `index.md`.

## Page 8

Image: [page-08.png](extracted/red-book-scan2/page-08.png)

- Mostly control-bit sketches, directional labels, and geometry notes.
- This aligns with the movement-bit breakdown described in [index.md](index.md).

## Pages 9-10

Images:

- [page-09.png](extracted/red-book-scan2/page-09.png)
- [page-10.png](extracted/red-book-scan2/page-10.png)

Heading on page 9:

- `KBORD INTERPRETATION`

Visible content from sampled page 9:

- Keyboard/joystick interpretation and movement application.
- Uses:
  - `(JOYST)`
  - `KEYIN`
  - `KEMPST`
  - `(KMOV)`
  - `(MOVED)`
  - `(OB1X)`
  - `(OB1Z)`
  - `(TKZ)`
  - `(SAUZ)`
  - `(MBZLC)`
  - `(HBZLC)`
  - `CALL ROTAT`
  - `CALL MESPR`

## Pages 11-16

Images:

- [page-11.png](extracted/red-book-scan2/page-11.png)
- [page-12.png](extracted/red-book-scan2/page-12.png)
- [page-13.png](extracted/red-book-scan2/page-13.png)
- [page-14.png](extracted/red-book-scan2/page-14.png)
- [page-15.png](extracted/red-book-scan2/page-15.png)
- [page-16.png](extracted/red-book-scan2/page-16.png)

Topic:

- `EXPLOSIONS`

Visible content from sampled page 11:

- Explosion data pointers `EXDT1` .. `EXDT6`
- Segment and point counts
- References to `LINCD`, `XTAB`, `ZTAB`, `YLOC`
- `CALL SCOPR`

Notes:

- These pages likely cover the segmented explosion systems for tank, missile, saucer, and other explodable objects.

## Page 17

Image: [page-17.png](extracted/red-book-scan2/page-17.png)

Headings:

- `CRASH`
- `SCOPR`

Visible content:

- Crash path uses:
  - `(DRTP?)`
  - `(SPPL)`
  - `(CRAVU)`
  - `(LINCD)`
  - `CALL LNLPT`
  - `CALL SDRAW`
  - `CALL DLAY1`
  - `(SHIPS)`
  - `(GAME OVER)`
  - `CALL MESPR`
  - `CALL ATTRT`
- Score path uses:
  - `(SCORE)`
  - `(MMAN)`
  - `(SHIPS)`
  - `(NMAN)`
  - `CALL NUMBA`

## Page 18

Image: [page-18.png](extracted/red-book-scan2/page-18.png)

Headings:

- `MESPR`
- `MESER`

Notes:

- `MESPR` is clearly a message-print routine taking a message address and copying character data.
- `MESER` appears to erase a message by writing zeros or blanks across the same area.

## Page 19

Image: [page-19.png](extracted/red-book-scan2/page-19.png)

Heading:

- `NUMBA`

Notes:

- This is the number-printing helper.
- Visible code references `NUMBERS`.

## Page 20

Image: [page-20.png](extracted/red-book-scan2/page-20.png)

- Mixed page of memory-layout notes, object sketches, and view-bucket notes.
- Visible references:
  - `message`
  - `line data`
  - `SPPL2`
  - `SPPL`
  - `VUA`, `VUB`, `VUC`, `VUD`, `VUE`

## Page 21

Image: [page-21.png](extracted/red-book-scan2/page-21.png)

Heading:

- `TABS`
- `LINCDS`

Visible content:

- Table labels include:
  - `TKTAB`
  - `STKTAB`
  - `MSTB`
  - `BULTB`
  - `OBTB`
  - `EXTRKT`
  - `EXSAT`
  - `EXMST`
  - `EXBLT`
- View-related labels include:
  - `TANK`
  - `STNK`
  - `SAUC`
  - `MISS`
  - `MBLVU`
  - `HBLVU`
  - `OB1VU`
  - `OB2VU`
  - `OB3VU`
  - `OB4VU`
  - `TKEXV`
  - `SAEXV`
  - `MSEXV`

Notes:

- This is one of the most valuable pages in the whole archive for mapping shape tables and visible-line tables.

## Page 22

Image: [page-22.png](extracted/red-book-scan2/page-22.png)

Heading/topic:

- Table memory locations

Legible labels include:

- `MATDATA`
- `TANDATA`
- `HILLDATA`
- `RADARDATA`
- `Hills Data`
- `HI SCORE`

## Pages 23-25

Images:

- [page-23.png](extracted/red-book-scan2/page-23.png)
- [page-24.png](extracted/red-book-scan2/page-24.png)
- [page-25.png](extracted/red-book-scan2/page-25.png)

Topic:

- Table locations from `45500`

Visible content from sampled page 23:

- `XTAB`
- `ZTAB`
- `YLOC`
- `SXLOC`
- `SZLOC`
- `SYLOC`
- `TXLOC`
- `STXLC`
- `MSXLC`
- `MBXLC`
- `HBXLC`
- `OBXLC`
- `SGXLC`
- `XPERS`
- `YPERS`

Notes:

- These pages look like offset maps for per-entity coordinate/perspective data blocks.

## Page 26

Image: [page-26.png](extracted/red-book-scan2/page-26.png)

- Diagram page with obstacle/viewpoint sketches and bit-pattern notes.
- Likely one of the viewpoint studies mentioned in `index.md`.

## Page 27

Image: [page-27.png](extracted/red-book-scan2/page-27.png)

Heading:

- `BLOOD!`

Visible text:

- `OBX`
- `DE = OBZ`

Notes:

- Only a couple of lines of code are present, matching Susan's note that this section is unfinished or continued elsewhere.

## Page 28

Image: [page-28.png](extracted/red-book-scan2/page-28.png)

- Not yet closely reviewed.
- Likely the unidentified code mentioned in [index.md](index.md).

## Immediate follow-up targets

- Tighten exact symbol spellings on pages 1-10 and 17-23.
- Pull the table labels from pages 21-25 directly into the shared symbol glossary.
- Map `NUMBA`, `MESPR`, `MESER`, `SCOPR`, `SCREEN`, and `KBORD INTERPRETATION` into `battlezone-skoolkit`.
