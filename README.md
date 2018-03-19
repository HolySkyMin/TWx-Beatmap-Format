# TWx Beatmap Format

This repository is to set the standard of the TWx Beatmap Format(TWx in short).

**Latest format version:** 2

## Format Specifications

## Intro

TWx is based on JSON format. It is hard to parse TXT based beatmap format (like BMS), but you can read JSON format using common well-known APIs in every languages. So it gets easier to use TWx to construct your game.

TWx is now accustomed to line-based rhythm games; in other words, the 1-dimension rhythm games. If your rhythm game has linear input line (no matter what the shape of line is), then you can use TWx in almost any situations.

## Structure

Simply say, TWx looks like this:

    {
        "version":2,
        "metadata":
        [
            "level":4,
            "artist":"TWx",
            "mapper":"thiEFcat",
            "density":30
        ],
        "notes":
        [
            {
                "ID":1,
                "Size":0,
                "Color":[255,255,255,255],
                "Mode":0,
                "Flick":0,
                "Time":1.0,
                "Speed":1.0,
                "StartLine":2.0,
                "EndLine":5.0,
                "PrevIDs":[0]
            },
            ...
        ]
    }

## Essential variables

Essential variables are variables which is necessary to run your games. If one value goes wrong, whole game will not be run.

**ID** *int*
Determines a note's ID.

**Size** *int*
Determines a note's size.
- 0: Small
- 1: Large
- 2: Special

**Color** *byte[4]*
