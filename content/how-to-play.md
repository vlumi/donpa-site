---
title: "How to play"
description: "Minesweeper from the first tap to forced guesses — the long version of Donpa Squad's in-app guide."
---

Donpa Squad is Minesweeper: a hidden minefield, numbers that tell the truth,
and one wrong tap. This is the long version of the in-app guide (the `?` on
the home screen) — same rules, more room to explain *why*.

## The goal

Open every tile that isn't a mine. Each revealed number counts the mines
touching that tile — including diagonals on square boards, or the six
neighbours on a Hive board.

```text
 ·  1  ■
 ·  2  ■
 ·  1  ■
```

Here the open tiles say everything: the `2` touches more mines than the `1`s,
and all of them can only be talking about the hidden column. Every deduction
in the game is this same move, repeated: *what do the numbers force?*

Your first dig of a game is always safe — it opens a starting region, never a
mine.

## Dig and flag

The corner toggle switches what a tap does:

- **Dig** opens the tile. This is the move that wins — and loses — games.
- **Flag** plants a marker on a suspected mine. Flags are your notes: the
  board never checks them, they can be wrong, and you can clear them freely.

A **long-press** does the other one — flag in Dig mode, dig in Flag mode (on
a revealed number it chords, like a tap). On a Mac, right-click is the same
"other action", so the toggle effectively assigns your two mouse buttons: Dig
mode gives the classic left-to-dig, right-to-flag.

You never *have* to flag. The win condition is opening every safe tile, so a
flagless game is not just possible but a recognized feat (see **Decorations**
in the Service Record).

Prefer a maybe-state? An optional **?** mark (Settings → Question marks)
turns the flag cycle into flag → ? → clear. A ? is only a note: it never
counts toward the mine counter and never satisfies a number for chording.

## Chording

The speed technique. When a revealed number already has exactly that many
flags beside it, tapping the **number itself** opens all of its remaining
neighbours at once.

```text
 ■  1  ·          ·  1  ·
 🚩 1  ·    →     🚩 1  ·
 ■  1  ·          ·  1  ·
```

The `1`s are satisfied by the flag, so chording them sweeps the rest of the
column in one tap. The bargain: a chord *trusts your flags*. If the flag was
wrong, the chord opens the mine — and the mistake was the flag, planted
seconds earlier, not the tap.

## The mine counter

The counter in the top bar is **mines minus flags** — how many mines you
haven't marked yet. It trusts your flags unconditionally, right or wrong,
which makes it a planning tool rather than an oracle: if it reads `2` with
three hidden tiles left, you know something about those tiles.

## Winning and losing

- **Win**: open the last safe tile. Flags don't need to be placed (or
  correct) — clearing is what counts.
- **Lose**: dig a mine. The game ends on the spot, but your cleared
  percentage still goes on the record — a 97% loss is a better run than a
  60% one, and the Service Record treats it that way.

## Forced guesses and luck

Sometimes Minesweeper stops being a logic puzzle for exactly one tap:

```text
 ·  1  ■
 ·  1  ■
```

Both 1s touch both hidden tiles: one mine, two identical candidates, and no
number anywhere that can ever tell them apart. That's a **forced guess** — the board made you gamble, and Donpa
tracks it honestly:

- When you survive a forced guess, the game stamps the **survival odds your
  tap had at that moment** — 50% above, worse in nastier positions (three
  tiles hiding two mines is a 1-in-3 pick; tangled endgame pockets can be
  worse). Survive a bad one and the result panel says so; your Service Record
  keeps a running luck line per board.
- Dying to a forced guess is fate, not error — the loss panel stamps the odds
  as consolation.

The fine print, because the numbers are honest: the tracking is **exact but
conservative**. A tap only counts as a forced guess when the game has
*proved* no safe move existed anywhere (or that a sealed pocket could never
be resolved by playing on). Positions too tangled to prove stay silent — so
every recorded guess carries true odds, and if the game says nothing about a
death, a safe move was still on the board somewhere. You just hadn't found
it.

Better than even odds isn't luck, by the way — surviving an 85% tap is
Tuesday. The toasts only celebrate coin flips and worse.

## Drills: practice without the dice

The **Drills** family (leftmost in New game, and where a fresh install
starts) generates boards that **never
force a guess** — every board is verified fully solvable by pure deduction
before you see it. Fixed 12% mine density, five sizes from XS to XL, with
their own best times.

It's the place to learn the patterns — the 1-2-1, the 1-2-2-1, wall reads —
and later, the place to speedrun them, because a no-guess board is a fair
stopwatch.

## Where to go from there

The board matrix **unlocks as you play**: bigger sizes, denser ranks, the
hexagonal Hive, and Round (wrap-around) edges each open on wins, and locked
options always show what opens them. Wins pin **Decorations** — 22
achievements from first blood to genuine feats — in your Service Record.
And when you're ready to compare notes, the **Mess hall** lets you swap
scores with rivals by QR code or link — or both ways at once with a player
in the same room (**Nearby**) — no accounts, no servers.

Questions the guide doesn't answer live on the [support page](/support/), and
bugs go to [GitHub](https://github.com/vlumi/donpa/issues).
