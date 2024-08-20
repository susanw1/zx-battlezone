### Original Documentation

These PDFs are scans of original design notes created between 1982-84 during the development of Quicksilva Battlezone.

Generally, the Z80 code was written down, tested by hand, and typed into a Spectrum assembler. Some (less complex) code was written straight into the assembler and the source probably no longer exists. Also amongst these scans are diagrams, comments and miscellaneous detritus from the design process.

Note that I was 17-18 when I wrote most of this, and Battlezone was the first big program I'd ever written. You've been warned.

Also note that I'm reading the titles and some of the symbols in the code to figure out what it does in the descriptions below. Don't take it as gospel though - it might be misleading. I didn't expect anyone would ever read these notes again, let alone put them on public display!

* Most of the code from 1983 was done in a red exercise book, scanned here in two parts for manageability. The quality is a bit low, because the spring binder somewhat jammed the scanner open - sorry. It should be adequate.
  * [Part 1](Red-book-scan1.pdf) (21 pages):
    * pg 1: "DIV system" - just some notes and sketches.
    * pg 2: Some unidentified code, with a little picture of a BZ view at top.
    * pg 3: "DE=X BZ=Z" unidentified code - lots of bit shifting. Might be to do with rotational transform?
    * pg 4: Rough notes: Probabilities of various entities appearing (eg, P(Tank|prev Missile) = 1/4), and bitfield defn of EXST1 and EXST2
    * pg 5-6: "Existences at start of wave", plus defn of MSTRJ and other missile vars
    * pg 7-10: "MAIN PROGRAM" - primary start point of game I think. PRSTA defn
    * pg 11-12: "TEXST" (Tank Existence) - I think this is deciding if to create a new tank 
    * pg 13-16: "TKSTRAT" (Tank Strategy) - how tank moves and attacks. Also headed as STKSTRAT (supertank strategy - was code same and shared?)
    * pg 17: "SAUC" - deciding if to create a saucer
    * pg 18: "SAUCSTRAT" - how the saucer moves
    * pg 19-20: "MISSILES" - deciding if to create a Missile
    * pg 21: "MISSTRAT" - Missile movement strategy
  * [Part 2](Red-book-scan2.pdf) (28 pages):
    * pg 1: "BULLT" - (my) bullet existence (bullet = shell)
    * pg 2: PRSTA defn again...? Some diagrams about min/max X
    * pg 3-4: "HBULLT" - (his = enemy) bullet existence
    * pg 5-6: "OBJECTS" - handling the 4 obstruction objects (2 cubes, pyramid, low-block)
    * pg 7: "SCREEN" - is this drawing the sights? Hills? (MHLPT and SHLPT look like hill-print or something)
    * pg 8: Breakdown of movement control bits, not sure which var (KMOV?)
    * pg 9-10: "KBORD INTERPRETATION" - applying movement
    * pg 11-17: "EXPLOSIONS" - handles the various explosions, code mostly duped for each explodable entity, with all its SEG segments
    * pg 17: "CRASH" - handles player-hit, dec SHIPS (=LIVES) etc. And, "SCOPR": updates scores
    * pg 18: "MESPR" - message printer. And "MESER" - not sure, message erase?
    * pg 19: "NUMBA" - something to do with Numbers, at a guess
    * pg 20: Some hard-to-decipher memory layout info, and possibly diagrams about visible views (VU)
    * pg 21: "TABS" and "LINCDS" - this is to do with tables of coords for different entities, and line definitions for different views
    * pg 22: Table memory locations for MATDATA (something maths-y?), TANDATA (prob inv-tangent table), HILLDATA (hills), RADARDATA (radar lines?)
    * pg 23-25: Table locations from 45500 for XTAB, ZTAB, and YLOC SXLOC etc. These are "locations" for all the different entities, not sure what they signify. Vertices? 
    * pg 26: Diagrams looking at viewpoints
    * pg 27: "BLOOD!" - start of the code handling the dripping blood. But only a couple of lines, then nothing; I remember this code written down somewhere else.
    * pg 28: unidentified code.

* Hill drawing code: [Hills.pdf](Hills.pdf) (4 pages)

* Not sure, probably some long-division code: [DIV.pdf](DIV.pdf) (5 pages)

* To be figured out! : [Eraser+Scanner.pdf](Eraser+Scanner.pdf) (2 pages)

* Some fixed global memory location symbols: [Mem-locations.pdf](Mem-locations.pdf)  (1 page)

* Locations of certain data regions: [Data-regions.pdf](Data-regions.pdf) (2 pages)
  * pg 1: Various data sets, eg the points and line definitions for the spinning QS logo and Battlezone title, the message area font (on top region during play), 1812 theme. Not sure why they're listed in a bizarre order.
  * pg 2: Really unsure what this is - seems to be some kind of inventory of parts. It's labelled "3)", but I can find no "2)" or "1)" on any other page. The table at the bottom is a history of my Spectrum ownership!

* Gameplay statistical rules defining which entities are created and how they move. Might supersede Red-book-part1 page 4 above : [Gameplay-stats.pdf](Gameplay-stats.pdf) (4 pages)

* Design diagrams for entities : [Entity-designs.pdf](Entity-designs.pdf) (4 pages)
