# Mem Locations Transcription

Source PDF: [Mem-locations.pdf](Mem-locations.pdf)

Extracted page image:

- [page-1.png](extracted/mem-locations/page-1.png)

Status: first pass

## Page 1

Image: [page-1.png](extracted/mem-locations/page-1.png)

This page is a compact symbol-to-address sheet for fixed memory locations.

Legible entries include:

- `SP1` -> `65024`
- `LINCD` -> `26`
- `LNCNT` -> `28`
- `SPPL` -> `30`
- `X1` -> `32`
- `X2` -> `34`
- `XD` -> `36`
- `Y1` -> `38`
- `Y2` -> `40`
- `YD` -> `42`
- `DRTP1` -> `44`
- `DRTP2` -> `46`
- `SPPL1` -> `48`
- `SPPL2` -> `50`
- `MAX1` -> `52`
- `MIN1` -> `54`
- `MAX2` -> `56`
- `MIN2` -> `58`
- `LIM1` -> `60`
- `LIM2` -> `62`
- `LIM3` -> `64`
- `LIM4` -> `66`
- `HLCNT` -> `68`
- `SHCNT` -> `70`
- `LIM` -> `72`
- `XLOC` -> `65074`
- `YLOC` -> `76`
- `ZLOC` -> `78`
- `XPERS` -> `80`
- `YPERS` -> `82`
- `XMAX` -> `84`
- `XMIN` -> `86`
- `DYCNT` -> `88`
- `XTAB` -> `90`
- `YTAB` -> `92`
- `ZTAB` -> `94`
- `MMAT` -> `96`
- `XDIS` -> `98`
- `ZDIS` -> `65100`
- `MUCNT` -> `02`
- `EXBLP` -> `04`
- `EXSCN` -> `06`
- `TRIGA` -> `08`
- `KMOV` -> `10`
- `SIGHT` -> `12`
- `SP2` -> `14`
- `TURN` -> `16`

Notes:

- The right-hand column strongly suggests the page is using offsets from base addresses `65024`, `65074`, and `65100`.
- Susan confirmed that the two-digit values are shorthand offsets from those base addresses.
- Susan confirmed `SP1` is temporary storage for the stack pointer when `SP` is reused as a general address register inside a routine; it must be restored before any `CALL`/`RET`.
- Susan suspects `SP2` serves the same purpose when `SP1` is already occupied in a caller.
- This is one of the highest-value scans for later disassembly mapping.
