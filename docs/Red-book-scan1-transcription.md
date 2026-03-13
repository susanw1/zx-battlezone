# Red Book Scan 1 Transcription

Source PDF: [Red-book-scan1.pdf](Red-book-scan1.pdf)

Extracted page images:

- [page-01.png](extracted/red-book-scan1/page-01.png)
- [page-02.png](extracted/red-book-scan1/page-02.png)
- [page-03.png](extracted/red-book-scan1/page-03.png)
- [page-04.png](extracted/red-book-scan1/page-04.png)
- [page-05.png](extracted/red-book-scan1/page-05.png)
- [page-06.png](extracted/red-book-scan1/page-06.png)
- [page-07.png](extracted/red-book-scan1/page-07.png)
- [page-08.png](extracted/red-book-scan1/page-08.png)
- [page-09.png](extracted/red-book-scan1/page-09.png)
- [page-10.png](extracted/red-book-scan1/page-10.png)
- [page-11.png](extracted/red-book-scan1/page-11.png)
- [page-12.png](extracted/red-book-scan1/page-12.png)
- [page-13.png](extracted/red-book-scan1/page-13.png)
- [page-14.png](extracted/red-book-scan1/page-14.png)
- [page-15.png](extracted/red-book-scan1/page-15.png)
- [page-16.png](extracted/red-book-scan1/page-16.png)
- [page-17.png](extracted/red-book-scan1/page-17.png)
- [page-18.png](extracted/red-book-scan1/page-18.png)
- [page-19.png](extracted/red-book-scan1/page-19.png)
- [page-20.png](extracted/red-book-scan1/page-20.png)
- [page-21.png](extracted/red-book-scan1/page-21.png)

Status: in progress

## Conventions

- Exact readings are written plainly.
- Uncertain readings are marked like `[unclear]`.
- Interpretation is kept separate from transcription.
- This file is a working companion to the scan, not yet a finished diplomatic transcript.

## Page 1

Image: [page-01.png](extracted/red-book-scan1/page-01.png)

Legible text:

- `DIV. SYSTEM`
- `XLOC = HL`
- `ZLOC = DE`
- `CNT = B`
- `X = A,A'`
- `Z = DE`
- `ANS = A,A'`
- `XPERS = SP`
- `FLAGS = C,C'`
- `PDD = HL`

Other visible content:

- Binary long-division style working near the top centre.
- Triangular sketch at top right.
- Small boxed note and a tiny routine block at lower right.

Interpretation:

- This looks like a notation/key page for the division or perspective system rather than executable code.

## Page 2

Image: [page-02.png](extracted/red-book-scan1/page-02.png)

Legible text:

- Top sketch shows a Battlezone-style viewport and hills.
- Rotation notes at top right appear to be of the form:
  - `x = x cos [theta] + z sin [theta]`
  - `z = z cos [theta] - x sin [theta]`
- Left-hand setup notes include:
  - `(DE = X)`
  - `(BC = Z)`
  - `A = 0,+0`

Visible code fragment:

- Starts with stack/register setup and then a repeated shift/add style sequence.
- The page is too faint for a reliable full line-by-line transcription on this pass.

Interpretation:

- This page appears to be transform or rotation-related maths/code, matching the sketch and formulae.

## Page 3

Image: [page-03.png](extracted/red-book-scan1/page-03.png)

Legible text:

- Heading-like note at top: `DE = X   BC = Z`
- Margin note: `C <- x`
- Margin note: `x sin [theta]`
- Bottom formulae appear to read:
  - `X = X cos [theta] + Z sin [theta]`
  - `Z = Z cos [theta] - X sin [theta]`

Visible code fragment:

- Continuation of a shift/add routine with `ADD HL,HL`, `SRL`, `BIT`, `JR`, `EX DE,HL`, `SBC HL,DE`, `POP`, `RET`.
- Too faint for a trustworthy complete transcription on this pass.

Interpretation:

- Almost certainly the rotational transform implementation.

## Page 4

Image: [page-04.png](extracted/red-book-scan1/page-04.png)

Legible text:

- `EXST1:`
- `7  old tank`
- `6  super tank`
- `5  saucer`
- `4  missile`
- `3  bullet (mine)`
- `2  bullet (his)`
- `EXST2:`
- `as above but`
- `explosions`

Other visible notes:

- Probability fractions in the middle and lower sections, including a cluster resembling:
  - `M = 1/4`
  - `M|M = 3/4`
  - `T = 3/4`
  - `T|M = 1/4`
- Lower-left note appears to include `G >= 25`.

Interpretation:

- This page is a compact state/probability note sheet covering entity existence flags and spawn odds.

## Page 5

Image: [page-05.png](extracted/red-book-scan1/page-05.png)

Legible text:

- Heading: `EXISTANCES AT START OF WAVE`
- Left column begins from `LD A,(EXST1)` and appears to derive new entity existence/state from score and random values.
- Mid/right side includes branches to named labels including:
  - `TSET`
  - `MSET`
- Lower-right block includes:
  - `CALL POLCO`
  - `LD (TKOR),HL`
  - `LD (TKDIR),HL`
  - `RET`

Interpretation:

- This looks like the wave-start entity creation logic, probably setting up the tank and missile starting state.

## Page 6

Image: [page-06.png](extracted/red-book-scan1/page-06.png)

Legible text:

- Top-left heading is faint but appears to be `MSET` or missile setup code.
- Clearly visible assignments include:
  - `LD HL,0`
  - `LD (MISX),HL`
  - `LD HL,-500`
  - `LD (MISY),HL`
  - `LD HL,25000`
  - `LD (MISZ),HL`
  - `LD HL,MISCT`
  - `LD A,(HL)`
  - `INC (HL)`
  - `LD (ZIG),A`
  - `LD A,128`
  - `LD (MSTRJ),A`
  - `SUB A`
  - `LD (MSMCT),A`
- Lower notes:
  - `MSTRJ`
  - `7 = [unclear]`
  - `6 = Left`
  - `5 = Back left`
  - `4 = Right`
  - `3 = Left return`
  - `2 = [unclear]`
  - `1 = [unclear]`
  - `0 = Down [left?]`
- Lower-right glossary:
  - `MSMCT = No. frame since manoeuvre`
  - `ZIG = No. of zigzags available`
  - `MISCT = No. of missiles so far`

Interpretation:

- This is missile initialization plus notes on the missile strategy/state variable meanings.

## Page 7

Image: [page-07.png](extracted/red-book-scan1/page-07.png)

Legible text:

- Large heading: `MAIN PROGRAM`
- Left column is a long block of initializations storing `HL` into many variables.
- Clear variable names visible in the first column include:
  - `(FRAME)`
  - `(EXST1)`
  - `(EXST2)`
  - `(SCORE)`
  - `(MISC?)`
  - `(PHASE)`
  - `(TKMCT)`
  - `(MSMCT)`
  - `(TRIGA)`
  - `(PRSTA)`
  - `(SHIP)`
  - `(OB1Z)`
  - `(OB2X)`
  - `(OB3X)`
  - `(OB3Z)`
  - `(OB4X)`
  - `(OB4Z)`
  - `SONTAB`
  - `(DRIPT1)`
  - `(SPPL1)`
  - `(DRIPT2)`
  - `(SPPL2)`
  - `(HLCNT)`
  - `(EXSCAN)`
  - `(OBOR)`
- Right column clearly includes:
  - `LD BC,607`
  - `LDIR`
  - `CALL MESPR`
  - `CALL HLSCORE`
  - `LD (MMAN),HL`

Interpretation:

- This is the startup/reset path for the core game state and probably the title/demo or new-game setup sequence.

## Page 8

Image: [page-08.png](extracted/red-book-scan1/page-08.png)

Legible text:

- Mostly numerical notes, diagrams, and address/value lists.
- Visible address list near top:
  - `53969 162`
  - `53971 164`
  - `53965 218`
  - `53967 220`
- Mid-page note:
  - `A = [illegible]`
  - `A' = 32 if x < z`
- Lower area contains viewpoint sketches and a starred radial diagram.

Interpretation:

- This page looks more like scratch maths or geometry notes than structured routine code.

## Page 9

Image: [page-09.png](extracted/red-book-scan1/page-09.png)

Legible text:

- Left margin references include:
  - `CALL TEXST`
  - `CALL EVPRO`
  - `CALL RADAR`
  - `CALL TKSTRAT`
  - `CALL MESER`
  - `CALL MESPR`
- Visible variable names include:
  - `(EXST2)`
  - `(EXST1)`
  - `(TKX)`
  - `(TKZ)`
  - `(TKSTR)`
  - `(OB1X)`
  - `(OB2Z)`
  - `(EXSCN)`
  - `(TKDIR)`
  - `(SPPL1)`
  - `(XTAB)`
  - `(ZTAB)`
  - `(SCOL?)`
  - `(ZI0C?)`
  - `(XDIS)`
  - `(ZDIS)`

Interpretation:

- This appears to be a chunk of the main loop that sequences entity existence, event processing, radar/messages, tank strategy, and table setup.

## Page 10

Image: [page-10.png](extracted/red-book-scan1/page-10.png)

Legible text:

- Top note appears to say:
  - `Conduct saucer existence`
  - `Set up bullets and missiles`
- `PRSTA`
- State mapping:
  - `7 Tank`
  - `6 Super Tank`
  - `5 Saucer`
  - `3 Bullet (mine)`
  - `1 Object`
  - `0 [unclear]`
  - `6 Super Tank`
  - `4 Missile`
  - `2 His Bullet`
- Lower-right obstacle sketches:
  - `OB1`
  - `OB2`
  - `OB3`
  - `OB4`
- Tank strategy note:
  - `(TKSTR) =`
  - `7 KILL`
  - `6 FORWARD`
  - `4 Left`
  - `5 Backw[ard]`
  - `3 Right`

Interpretation:

- This is a mixed design-notes page: state layout, object sketches, and strategy encoding notes.

## Page 11

Image: [page-11.png](extracted/red-book-scan1/page-11.png)

Legible text:

- Heading: `TEXST`
- Visible variable names and labels include:
  - `(FRAME)`
  - `(PRSTA)`
  - `MSET`
  - `(EXST1)`
  - `(TKZ)`
  - `(SAUZ)`
  - `(SAUX)`
  - `(EXST2)`
  - `(TRIGA)`
  - `(MAX2+1)`
  - `(MIN2-1)`
  - `(OB1X-1)`
  - `(OB1Z)`
  - `(OB2Z)`
  - `(TKSTR)`
  - `(TKOR)`
  - `(TKDIR)`
  - `(HBLOR)`
  - `(HBLCT)`
  - `(HBLX)`
  - `(HBLZ)`
  - `(HBULZ)`
  - `(EXT)`
- Visible logic suggests testing whether a tank should exist, choosing coordinates, and initializing hostile-bullet state.

Interpretation:

- This is clearly the tank-existence / tank-spawn routine and likely a useful early target for annotation in `battlezone-skoolkit`.

## Page 12

Image: [page-12.png](extracted/red-book-scan1/page-12.png)

Legible text:

- Page continues from `TEXST`.
- Top note: `For OB3`
- Visible variables and tables include:
  - `(OB3X)`
  - `(OB3Z-1)`
  - `(MAX)`
  - `(MIN)`
- Visible arithmetic/logic sequence includes:
  - `ADD 32`
  - `SUB 64`
  - `JP C`
  - `JP NC`
  - `SRL H`
  - `RR L`
  - `EX DE,HL`
  - `ADC HL,DE`
  - `JP P`
  - `AND 253`
  - `RRA`

Other visible content:

- Small object sketches on the right side.
- Top-centre viewpoint sketch.

Interpretation:

- This looks like the obstacle-position / obstacle-visibility side of `TEXST`, probably checking whether obstacle 3 is within the permitted spawn/visibility window.

## Page 13

Image: [page-13.png](extracted/red-book-scan1/page-13.png)

Legible text:

- Heading: `(S)TKSTRAT`
- Visible variables and labels include:
  - `(TKMCT)`
  - `(TKSTR)`
  - `(TKOR)`
  - `(TKX)`
  - `(TKZ)`
  - `(TZLOC+2)`
  - `(TZLOC+14)`
  - `(TXLOC+10)`
  - `(TXLOC+2)`
  - `(FRAME)`
  - `(PHASE)`
  - `(TKDIR)`
- Right-edge notes:
  - `LD A,(TKSTR)`
  - `LD A,255`
  - `LD (TKMCT),A`
- Lower-left strategy legend appears to include:
  - `TKSTR`
  - `7: kill`
  - `5: back`
  - `3: right`
  - `4: left`
  - `2 [unclear]`
  - `0 [unclear]`

Interpretation:

- This is the tank strategy routine proper, using tank state plus table-derived positional deltas to decide movement and facing.

## Page 14

Image: [page-14.png](extracted/red-book-scan1/page-14.png)

Legible text:

- Mostly diagrammatic page.
- Visible numeric annotations include:
  - `128`
  - `120`
  - `135`
  - `220`
  - `242`
  - `400`
- Contains repeated small tank/object orientation sketches and viewpoint arrows.

Interpretation:

- This appears to be design support for `TKSTRAT`: orientation/view geometry and perhaps angle buckets or tactical cases, rather than direct code.

## Page 15

Image: [page-15.png](extracted/red-book-scan1/page-15.png)

Legible text:

- Continuation of `TKSTRAT`.
- Visible calls and labels include:
  - `CALL MATOLT`
  - `CALL MATRT1`
  - `CALL PERSP`
  - `CALL DLAY1`
  - `CALL LNLPT`
  - `JP SAUC`
  - `STNK`
- Visible variables include:
  - `(TKOR)`
  - `(RBEEP)`
  - `TYLOC`
  - `(YLOC)`
  - `TKXPER+32`
  - `(XPERS)`
  - `VU-A`
  - `VU-B`
  - `VU-C`
  - `VU-D`
  - `VU-E`
  - `(LINCD)`
  - `(SPPL)`
  - `(PRSTA)`
  - `(MAX)`
  - `(MIN)`
  - `SAUC`

Interpretation:

- This page looks like the rendering/visibility side of the tank routine: perspective setup, view selection (`VU-*`), line-table selection, and then handoff to the saucer routine.

## Page 16

Image: [page-16.png](extracted/red-book-scan1/page-16.png)

Legible text:

- Continuation note at top: `- contd`
- Visible variables and calls include:
  - `(TKOR)`
  - `(RBEEP)`
  - `TYLOC`
  - `(YLOC)`
  - `TKXPER+32`
  - `(XPERS)`
  - `CALL PERSP`
  - `(PRSTA)`
  - `CALL DLAY1`
  - `(MAX)`
  - `(MIN)`
  - `CALL LNLPT`
  - `(SPPL)`
  - `JP SAUC`
- Right-side view-selection block again refers to:
  - `VU-A`
  - `VU-B`
  - `VU-C`
  - `VU-D`
  - `VU-E`

Interpretation:

- Another `TKSTRAT` continuation page, reinforcing that view-bucket selection and line plotting are baked directly into the strategy/render pipeline.

## Page 17

Image: [page-17.png](extracted/red-book-scan1/page-17.png)

Legible text:

- Heading: `SAUC`
- Visible variables and labels include:
  - `(EXST1)`
  - `MISS`
  - `(SAUOR)`
  - `SHSING`
  - `(SPPL)`
  - `SXLOC`
  - `SZLOC`
  - `SZLOC1+12`
  - `(SAUZ)`
  - `SXPER`
  - `SYPER`
  - `(YLOC)`
  - `CALL PERSP`
  - `(PRSTA)`
  - `CALL DLAY1`
  - `(MAX)`
  - `(MIN)`
  - `CALL LINCD`
  - `CALL LNLPT`
  - `JP BULLT`

Interpretation:

- This is the saucer existence/setup and draw path, ending by transferring control to the bullet routine.

## Page 18

Image: [page-18.png](extracted/red-book-scan1/page-18.png)

Legible text:

- Heading: `SAUSTRAT`
- Visible variables and state include:
  - `(SAMCT)`
  - `(SAUX)`
  - `(SAUXC)`
  - `(SAUZ)`
  - `(TXZ)`
  - `32768`
- Visible operations include:
  - `DEC A`
  - `LD (SAMCT),A`
  - `ADD HL,DE`
  - `LD (SAUZ),HL`
  - `RET`
  - `LD A,80`
  - `RLA`
  - `AND A`
  - `JP P`
  - `EX DE,HL`
  - `SBC HL,DE`
  - `LD (SAUX),HL`
  - `RET`

Interpretation:

- This appears to move the saucer on a timer/counter basis and adjust its X/Z motion, probably alternating or randomizing sweeps.

## Page 19

Image: [page-19.png](extracted/red-book-scan1/page-19.png)

Legible text:

- Heading: `MISSILES`
- Visible variables and calls include:
  - `(EXST1)`
  - `BULLT`
  - `CALL MISSTRAT`
  - `(MSTRJ)`
  - `(MISX)`
  - `(MISZ)`
  - `CALL RADAR`
  - `(MISZ-1)`
  - `CALL MESPR`
  - `CALL POLCO`
  - `(EXSCN)`
  - `(BEEP?)`
  - `XTAB`
  - `ZTAB`
  - `(MXLOC)`
  - `(MLOC?)`
  - `(MZLOC)`
  - `(MSOR)`
  - `CALL MATMCT`
  - `(XPERS)`
  - `(YPERS)`
  - `(SPI)`
  - `CALL PERSP`
  - `(PRSTA)`
  - `CALL DLAY1`
  - `(MAX)`
  - `(MIN)`

Interpretation:

- This is the missile existence/render path: invoke missile strategy, update radar/messages, derive transformed coordinates, then run perspective and visibility checks.

## Page 20

Image: [page-20.png](extracted/red-book-scan1/page-20.png)

Legible text:

- Continuation note at bottom: `BULLT`
- Lower strategy legend:
  - `MSTRT`
  - `7 init drop`
  - `6 left`
  - `5 right return`
  - `4 right`
  - `3 left return`
  - `2 up`
  - `1 [centre? / straight?]`
  - `0 down`
- Visible variables and view/render terms include:
  - `(MIN)`
  - `(PRSTA)`
  - `(SHIP)`
  - `(MXPER+12)`
  - `VU-A`
  - `VU-B`
  - `VU-C`
  - `(LINCD)`
  - `(SPPL)`

Other visible content:

- Large sketches of obstacle/object shapes in the right half of the page.

Interpretation:

- This looks like a continuation of the missile handling code plus a more explicit legend for the missile strategy state values.

## Page 21

Image: [page-21.png](extracted/red-book-scan1/page-21.png)

Legible text:

- Heading: `MISSTRAT`
- Visible variables include:
  - `(MSTRT)`
  - `(MISY)`
  - `(MISC?)`
  - `(MSOR)`
  - `(MISZ+1)`
  - `(MIST?)`
  - `(OB2X+1)`
  - `(MISX+1)`
  - `(MISZ+1)`
  - `ZIG`
- Visible control/state operations include repeated blocks of:
  - `BIT 6,C`
  - `RES 6,C`
  - `SET 5,C`
  - `SET 6,C`
  - `RES 5,C`
  - `BIT 4,C`
  - `BIT 5,C`
  - `BIT 3,C`
  - `LD HL,(MSOR)`
  - `LD DE,65408`
  - `LD DE,108`
  - `LD DE,64`
  - `LD DE,65472`
  - `ADD HL,DE`
  - `LD (MSOR),HL`
  - `DEC (HL)`
  - `RETNC`
  - `RET`

Interpretation:

- This is the missile movement state machine, using bitfields inside the strategy byte and repeatedly adjusting missile orientation / movement offsets via `MSOR`.

## Coverage note

All pages now have at least a first-pass heading/topic capture and a small amount of extracted content.

What remains is a second pass for:

- exact line-by-line transcription where legibility permits,
- normalization of symbol spellings,
- cross-mapping these notebook identifiers into the current SkoolKit disassembly.

## Immediate follow-up targets

- Tighten the exact transcription on pages 11-21.
- Normalize symbol names across this file, `zx-battlezone/README.md`, and `battlezone-skoolkit`.
- Start a symbol glossary once the routine names from pages 11-21 are captured more completely.
