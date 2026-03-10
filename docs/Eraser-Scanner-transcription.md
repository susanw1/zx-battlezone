# Eraser And Scanner Transcription

Source PDF: [Eraser+Scanner.pdf](Eraser+Scanner.pdf)

Extracted page images:

- [page-1.png](extracted/eraser+scanner/page-1.png)
- [page-2.png](extracted/eraser+scanner/page-2.png)

Status: first pass

## Page 1

Image: [page-1.png](extracted/eraser+scanner/page-1.png)

Heading:

- `ERASER`

Visible variables and pointers:

- `(SPPL)`
- `(DRTP2)`
- `(SP1)`
- `(SPPL1)`
- `(LIM3)`
- `(HLCNT)`

Notes:

- This appears to erase or clear previously drawn material using stored pointers and loop counts.
- The repeated stores to `(HL)` and `(DE)` suggest buffer wiping or redraw cleanup.

## Page 2

Image: [page-2.png](extracted/eraser+scanner/page-2.png)

Heading:

- `SCANNER`

Visible variables and pointers:

- `(EXBLP)`
- `(SP1)`
- `(EXSCN)`
- `(XLOCBL)` `[unclear]`
- `(XLOC)`

Notes:

- This looks like a scanline or explosion/scan effect helper.
- The repeated reads from tables and writes via `EXBLP` suggest a generated effect rather than ordinary entity drawing.
