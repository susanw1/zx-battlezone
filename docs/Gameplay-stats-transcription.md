# Gameplay Stats Transcription

Source PDF: [Gameplay-stats.pdf](Gameplay-stats.pdf)

Extracted page images:

- [page-1.png](extracted/gameplay-stats/page-1.png)
- [page-2.png](extracted/gameplay-stats/page-2.png)
- [page-3.png](extracted/gameplay-stats/page-3.png)
- [page-4.png](extracted/gameplay-stats/page-4.png)

Status: first pass

## Page 1

Image: [page-1.png](extracted/gameplay-stats/page-1.png)

Heading:

- `EXSTENCES` or `EXSTENCES` `[spelling as written]`

Visible sections:

- `TANK`
- `SUPER TANK`
- `MISSILE`
- `SAUCER`

Visible probability notation:

- `P(T)`
- `P(ST)`
- `P(T|M)`
- `P(M)`
- `P(M|M)`
- `P(saucer) = 1/1`

Notes:

- This page appears to formalize the spawn/existence rules sketched more roughly in `Red-book-scan1`.
- Score thresholds such as `S <= 4` and `S >= 25` are visible.

## Page 2

Image: [page-2.png](extracted/gameplay-stats/page-2.png)

Heading:

- `STRATEGEMS`

Visible sections:

- `TANK`
- `SUPERTANK`

Legible notes include:

- `Turn around only and for 50-215 cycles`
- `turn and look`
- `turn around`
- `forward`
- `As above - but limit on turning`

Probability notes:

- Several expressions of the form `P = ... / 512`

Notes:

- This page appears to quantify tank and supertank behavior selection.
- It aligns with Susan's recollection that tanks can trundle, stop, and become aggressive, with supertanks sharing most logic.

## Page 3

Image: [page-3.png](extracted/gameplay-stats/page-3.png)

Heading:

- `MISSILE`

Legible notes include:

- `M = No. of missiles fired so far`
- `One zigzag =`
- `Start at (0, 2400, 25600)`
- `Drop at rate`
- `When Y = 0`
- `On zigzag, X vector is +/- 300 for 4 frames`
- `But chance of a zig = 3/4`
- `If object is ahead ... climb ... for 3 frames`
- `then down ... for 3 frames`

Notes:

- This page is especially important because it directly corroborates Susan's recollection:
  - missile zig-zags increase with missile count,
  - the missile returns to its original path,
  - obstacle avoidance uses an up/down hop.

## Page 4

Image: [page-4.png](extracted/gameplay-stats/page-4.png)

Heading:

- `SAUCER`

Legible notes include:

- `-32768 < Xs < 32767`
- `Zs -> Zs + [constant]`
- `Xs -> Xs + [random or signed delta]`
- `Zs = const for 50 frames`
- `Xs = +/- RND for 50 frames`

Other content:

- Large numeric tables or byte-value lists across the lower half of the page.

Notes:

- This looks like both a high-level saucer movement spec and an associated table dump.
