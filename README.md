# zx-battlezone
Battlezone, released by Quicksilva in 1984

### Original Design Notes

See [document index](docs/index.md).

This follows from discussions here: [https://spectrumcomputing.co.uk/forums](https://spectrumcomputing.co.uk/forums/viewtopic.php?t=11933)

### How did it work?

This is based on my recollection from 40 years ago. We can update this if it's wrong...

Basic facts:
* All machine code, no basic.
* Disabled interrupts at the start and regularly used SP as an address register for stepping through tables.
* Drawing is done on an offscreen buffer and LDIR'ed to the display.
  * I was unaware of performance issues around accessing lower RAM during display update.
  * I never realized that LDIR was suboptimal, or that clearing the buffer could be done far quicker. Super-annoying, as I think buffer copying/clearing is the dominant time hog, overwhelming all the other performance optimizations I did elsewhere, at great cost to intelligibility and development time.
* The coord system is signed 16-bit x,y,z, so +/-32768 in all axes - though nothing rotates in the y-axis, so only X-Z rotates. I think all angles were 8-bit 0-255. View is limited to only draw objects between a near and far limit (perhaps 3000<Z<30000?).
* Coord system is _always_ centred on the player! Player is always at 0,0,0 staring down the Z-axis, and when the player moves and spins, in reality the entities in the world move and spin. Cumulative error over a long game can lead to surprises.
* There are 4 obstacle objects (two cubes, pyramid and low block), initially positioned at (+/-16384, +/-16384). Only one object is ever visible at a time.

The execution of the Game Loop broadly performs the following steps:
* Determine which entities need to be created depending on game state.
* Apply "strategies" (uses ATAN2 table for aiming/firing).
* Generate line endpoints to be drawn:
  * Take vertices ("points") of enemy tank or supertank (3 lists of X,Y,Z values (8? 16? bit, can't recall)) and perform z' = z cos A + x sin A; x' = x cos A - z sin A using a trig table and fully unrolled 16-bit long binary multiplication. (Massive overkill in terms of precision, and I was unaware of neat multiplication tricks).
  * Offset the vertices for enemy tank to the correct X,Y,Z location in the world.
  * Determine that object has near<Z<far, if so, generate perspective vertices, X = x'/z', Y = y'/z' using full unrolled 16-bit long division. Again, overkill on precision and unaware of tricks. This produces lists of 16-bit X,Y line endpoints to be clipped and drawn.
  * Repeat all steps for Saucer, Missile, My bullet (player's shell), His bullet (enemy shell), Objects 0-3, and any explosion segments.
* Clear the offscreen buffer
* For each visible entity, determine its "View" to select just the set of lines that would be visible (primitive hidden line removal to save on unneeded line drawing).
* Draw the lines to the buffer: calculate gradient using binary long division and using Bresenham's line algorithm. Clipping done naively by just not plotting points that are offscreen. Algorithm implemented as 6 separate handlers for lines with gradiant angles 0º, 0º<A≤45º, 45º<A<90º, 90º, 90º<A≤135º, 135º<A<180º, I think.
* Draw the background hills to buffer, without overwriting objects.
* Draw target sights to buffer.
* Draw messages ("Motion Obstructed" "Enemy to left"), score, and update radar on the top part of the screen.
* Copy the buffer to the screen.
* Check keyboard and joystick and update control status.
* Apply controls to world.
* Perform collision detection between player, enemies, shells and obstacles.
* Repeat.

The ordering of the above steps is probably not quite right. FIXME.
