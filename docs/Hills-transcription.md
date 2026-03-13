# Hills Transcription

Source PDF: [Hills.pdf](Hills.pdf)

Extracted page images:

- [page-1.png](extracted/hills/page-1.png)
- [page-2.png](extracted/hills/page-2.png)
- [page-3.png](extracted/hills/page-3.png)
- [page-4.png](extracted/hills/page-4.png)

Status: first pass

## Overview

This scan contains the hill-drawing code. It uses `MAX1`, `MIN1`, `MAX2`, `MIN2`, `LIM1`..`LIM4`, `HLCNT`, and stack-temporary pointers to generate and draw hill segments.

## Page 1

Image: [page-1.png](extracted/hills/page-1.png)

Heading:

- `HILLS 1`

Visible variables:

- `(MAX1)`
- `(MIN1)`
- `(MAX2)`
- `(MIN2)`

Notes:

- This page appears to derive span limits or clipped bounds for hill segments.

## Page 2

Image: [page-2.png](extracted/hills/page-2.png)

Visible variables:

- `(SP1)`
- `(HLCNT)`
- `(LIM1)`
- `(LIM2)`

Notes:

- This page looks like the main hill-writing loop into screen/buffer memory.

## Page 3

Image: [page-3.png](extracted/hills/page-3.png)

Visible variables:

- `(HLCNT)`
- `(LIM2)`
- `(LIM1)`
- `(LIM3)`

Notes:

- Continuation of the drawing loop with more limit handling and memory writes.

## Page 4

Image: [page-4.png](extracted/hills/page-4.png)

Visible labels and notes:

- `SHL2`
- `HILLS DATA`
- `N = 32002`
- `X = 32005`
- `1 SAUPNT, 2 SAUPNT, 3 SAUPNT, 4 SAUPNT` `[unclear exact reading]`

Notes:

- This page appears to finish the hill loop and document the hill-data layout.
