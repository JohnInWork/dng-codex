# [LPC] Medieval Village Decorations

- Source: <https://opengameart.org/content/lpc-medieval-village-decorations>
- Package: `decoration_medieval.zip`
- Imported: 2026-09-20
- License: **CC-BY-SA 3.0+**

"[LPC] Medieval Village Decorations" by bluecarrot16, Lanea Zimmerman (Sharm),
Reemax (Tuomo Untinen), Xenodora, Johann C, Johannes Sjölund, Casper Nilsson,
Daniel Cook, Rayane Félix (RayaneFLX), Wolthera van Hövell tot Westerflier
(TheraHedwig), Hyptosis, mold, Zachariah Husiar (Zabin), Clint Bellanger,
Jetrel, Nemisys, Guido Bos, Curt, Bertram, and Daniel Eddeland (daneeklu).
License: CC-BY-SA 3.0+.

The full upstream credit chain — every submission these tiles were assembled
from, with its own author and license — is kept verbatim in
[`CREDITS-decorations-medieval.txt`](CREDITS-decorations-medieval.txt) beside
this file. The upstream notice says **all information in that file must be
included**; it travels with the art and is not edited.

## Why this pack is here

Dungeon Crawl Stone Soup is a dungeon crawler: its 3 455 tiles contain no
streets and therefore no street furniture at all. The town this game has was
being furnished out of a tavern's indoor fittings — campfires for street
lamps, and one single shop sign for every shop. This pack is the town.

## What is here

Both upstream sheets are shipped whole and unmodified:

- `decorations-medieval.png` — 16×64 tiles: graveyard, statues, wells, hanging
  shop signs (blade, potion, bread, amulet, book, beer, INN, jewellery, tools),
  wall lanterns and candles, market stalls with awnings, carts, hay, woodpiles,
  anvils, crates, benches, fences.
- `fence_medieval.png` — 16×32 tiles of fencing and gates.

The renderer asks for one sprite per path, so the tiles the game actually draws
are cut out of these sheets into `cut/` as they are chosen. A cut tile is a
modification of CC-BY-SA material and is itself CC-BY-SA 3.0+; keeping the cuts
inside this directory keeps that obvious.

These files are **not** covered by the CC0 dedication that applies to the
surrounding Dungeon Crawl Stone Soup library.

## Modified cuts

- `cut/bandage-cloth.png` — the linen hanging on a washing line, cut from
  `decorations-medieval.png` at (355, 138)–(382, 155), with a 9×9 red cross
  painted on in the red of the library's curing-potion mark. It is the icon of
  the game's bandages (chosen by Ivan, 03.10.2026). A modification of CC-BY-SA
  material, so it is CC-BY-SA 3.0+ like every other file in `cut/`.
- `cut/sign-scroll.png`, `cut/sign-wand.png`, `cut/sign-temple.png` — the
  blank hanging sign `cut/sign-blank.png` with a scroll, a wand with a star,
  and a temple front painted on pixel by pixel in the four golds the pack's
  own signs are drawn in, centred where their marks hang. They are the signs
  of the city's scribe, wandmaker and temple (05.10.2026): the pack has no
  scroll or wand sign, and its book now hangs over the bookseller. Generated
  by `tools/atlas/derive-signs.py`. A modification of CC-BY-SA material, so
  CC-BY-SA 3.0+ like every other file in `cut/`.

## Cemetery cut (`graves/`, 2026-10-08)

The headstones, crosses, graves and statues on the top-left of
`decorations-medieval.png` are by Reemax ("[LPC] Signposts, graves, line cloths
and scare crow", CC-BY-SA 3.0 / GPL 3.0 — the credit is already in the chain
file above). `tools/atlas/cut-lpc-graves.py` cuts them into `graves/*.png`, one
picture each on a square 32/64/96 canvas, a little darker and cooler so the
stone sits next to the masonry of the city; the game uses six of them in front
of the way down. License and credit are unchanged.
